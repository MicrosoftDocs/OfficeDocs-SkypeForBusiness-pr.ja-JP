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
# <a name="deploy-skype-room-systems-v2-management-with-azure-monitor"></a>Azure のモニターを使用して Skype ルーム システム v2 の管理を展開します。

この資料を設定し、Azure のモニターを使用して Skype ルーム システム v2 のデバイスの統合された、エンド ・ ツー ・ エンドの管理を展開する方法について説明します。

基本的な遠隔測定を提供する Azure モニター内でのログの分析を構成することができ、警告するためは、Skype の会議室のデバイスを管理します。 管理ソリューションが完成に近づくにつれて、追加のデータとデバイスの可用性とパフォーマンスの詳細なビューを作成する管理機能を導入することができます。

によって、このガイドに従うと、デバイスの可用性、アプリケーションとハードウェアの健康状態、および Skype ルーム システム v2 アプリケーションおよびオペレーティング システムのバージョンの配布用のレポート、詳細なステータスを取得するのに例を次のようなダッシュ ボードを使用できます。

![SRS v2 のサンプル ログ分析の表示](../../media/Deploy-Azure-Monitor-1.png "SRS v2 のサンプル ログ分析の表示")

高いレベルでは、次のタスクを実行する必要があります。


1.  [ログ分析の構成を検証します。](azure-monitor.md#validate_LogAnalytics)
2.  [管理セットアップのログ分析機能のテスト デバイスを構成します。](azure-monitor.md#configure_test_devices)
3.  [カスタム フィールドをマップする](azure-monitor.md#Custom_fields)
4.  [ログ分析で Skype ルーム システム v2 ビューを定義します。](azure-monitor.md#Define_Views)
5.  [警告を定義します。](azure-monitor.md#Alerts)
6.  [監視のすべてのデバイスを構成します。](azure-monitor.md#configure_all_devices)
7.  [Azure のモニターの追加のソリューションを構成します。](azure-monitor.md#Solutions)

> [!IMPORTANT]
> Skype ルームのすべてのシステムにエージェントの展開を開始する前に実行する必要があるいくつかの Skype ルーム システム v2 固有の手順はまだありますが、最小限の構成では、Azure 監視ログ分析機能は、Windows オペレーティング システムを実行するコンピューターを監視できます、デバイスです。
> したがって、コントロールのセットアップと構成の正しい順序ですべての構成手順を実行するを強くお勧めします。 最終結果の品質は、初期構成の品質に非常に依存します。

## <a name="validate-log-analytics-configuration"></a>ログ分析の構成を検証します。
<a name="validate_LogAnalytics"> </a>

Skype ルーム システム v2 のデバイスからのログの収集を開始するログ分析機能のワークスペースが必要です。 ワークスペースは、独自のデータ リポジトリ、データ ソース、およびソリューションの一意なログ分析環境です。 既にした場合、既存のログ分析機能のワークスペース、Skype ルーム システム v2 配置を監視するために使用可能性があります代わりを作成したりできます、専用のログ分析機能のワークスペース特定 Skype ルーム システム v2 の監視ニーズにします。

[Azure ポータルでのログの分析機能のワークスペースを作成する](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)この資料の指示に従って、新しいログの分析機能のワークスペースを作成する場合は、

> [!NOTE]
> ログ分析機能を使用して、Azure のモニターでは、Azure サブスクリプションはアクティブにする必要があります。 Azure サブスクリプションをお持ちでない場合は、開始点として[無料の試用版サブスクリプション](https://azure.microsoft.com/free)を作成できます。

### <a name="configure-log-analytics-to-collect-skype-room-systems-v2-event-logs"></a>Skype ルーム システム v2 のイベント ログを収集するログの分析を構成します。

のみ、ログ分析機能は、設定で指定されている Windows のイベント ログからイベントを収集します。 各ログには、選択した重大度のレベルのイベントのみが収集されます。

Skype ルーム システム v2 のデバイスとアプリケーションの状態を監視するために必要なログを収集するログの分析を構成する必要があります。 Skype ルーム システム v2 のデバイスでは、 **Skype の部屋のシステム**イベント ログを使用します。

Skype ルーム システム v2 のイベントを収集するログの分析を構成するには、 [Azure のモニターでは、Windows イベント ログ データ ソース](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)を参照してください。

![イベント ログの設定](../../media/Deploy-Azure-Monitor-2.png "イベント ログの設定")

> [!IMPORTANT]
> Windows イベント ログ設定を構成および**Skype ルーム システム**を入力して、イベント ログの名前と、**エラー**、**警告**、および**情報**のチェック ボックスをオンします。

## <a name="configure-test-devices-for-azure-monitoring"></a>Azure を監視するためのテスト デバイスを構成します。
<a name="configure_test_devices"> </a>

Skype ルーム システム v2 に関連するイベントを監視することができるログの分析を準備する必要があります。 開始する物理的なアクセス権を持つ、1 つか 2 つの Skype ルーム システム v2 デバイスに Microsoft の監視エージェントを展開し、それらを取得する必要がありますテスト デバイスは、いくつかのデータを生成し、ログ分析機能のワークスペースに押し込みます。

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>デバイスをテストするのには Microsoft の監視エージェントをインストールします。

テスト デバイスに[接続の Windows コンピューター](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)で提供されている手順を使用して Microsoft の監視エージェントを展開します。 この資料には、監視エージェントの Windows を展開するための手順に関する詳細情報が用意されています、Skype ルーム システム v2 のデバイスを取得するログ分析機能の***ワークスペース ID***と***プライマリ ・ キー***を取得するための手順に接続されています。Azure のモニターの配置とログ分析のインスタンスへのエージェント接続を確認する手順を実行します。

### <a name="generate-sample-skype-room-systems-events"></a>サンプル Skype ルームのシステム イベントを生成します。

Microsoft の監視エージェントがテストのデバイス上に配置されると、Azure のモニターを使用して必要なイベント ログ データを収集することを確認します。

> [!NOTE]
> 、Microsoft の監視エージェントのインストール後、デバイスを再起動し、その Skype ルーム システム v2 の会議アプリケーションを起動すると、イベント ログに新しいイベントが生成されることができるようにします。

1.  [Microsoft Azure ポータル](https://portal.azure.com)にサインインし、どうなるログの分析に新しいワークスペースを選択します。

2.  Skype ルーム システム v2 デバイスによって生成されたハートビート イベントを一覧表示します。
    1.  ワークスペースを選択して**ログ**にしてどうなる SRS v2 のカスタム フィールドがあるハートビート レコードを取得するクエリを使用します。
    2.  サンプル クエリ。`Event | where Source == "SRS-App" and EventID == 2000`

3.  Skype ルーム システム v2 の会議アプリケーションによって生成されたイベントを含むログ レコードをクエリが返すことを確認します。

4.  ハードウェアの問題を生成し、Azure のログの分析に必要なイベントを記録することを検証します。
    1.  Skype ルーム システム v2 のシステムのテストで周辺機器の 1 つを外します。 カメラ、スピーカー フォン、マイク、または部屋の前面表示可能性があります。
    2.  Azure のログ分析機能に設定するイベント ログの 10 分間待ちます。
    3.  ハードウェア エラー イベントのリストにクエリを使用します。`Event | where Source == "SRS-App" and EventID == 3001`

5.  、アプリケーションの問題を生成し、必要なイベントを記録することを検証します。
    1.  Skype ルーム システム v2 アプリケーションの構成を変更し、不正なセッション開始プロトコル (SIP) アドレスとパスワードのペアを入力します。
    2.  Azure のログ分析機能に設定するイベント ログの 10 分間待ちます。
    3.  アプリケーション エラー イベントのリストにクエリを使用します。`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> ユーザー設定フィールドを構成する前に、これらのサンプルのイベント ログが必要です。 必要なイベント ログを収集し終えるまで、次の手順を続行しません。

## <a name="map-custom-fields"></a>カスタム フィールドをマップする
<a name="Custom_fields"> </a>

イベント ログから特定のデータを抽出するのにには、カスタム フィールドを使用します。 タイル、ダッシュ ボードの表示、および警告の後で使用するカスタム フィールドを定義する必要があります。 [ログ分析でユーザー設定フィールド](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields)を参照してくださいし、カスタム フィールドの作成を開始する前に概念を理解します。

キャプチャしたイベント ログから、ユーザー設定のフィールドを抽出するには、以下の手順を実行します。

1.  [Microsoft Azure ポータル](https://portal.azure.com)にサインインし、どうなるログの分析に新しいワークスペースを選択します。

2. Skype ルーム システム v2 デバイスによって生成されたイベントの一覧を表示します。
   1.  **(クラシック) のログ**に移動し、ユーザー設定フィールドを持つレコードを取得するクエリを使用します。
   2.  サンプル クエリ。`Event | where Source == "SRS-App" and EventID == 2000`

3. レコードのいずれかを選択、左側にあるボタンを選択し、フィールドの展開ウィザードを起動します。

   ![フィールドの抽出ウィザード](../../media/Deploy-Azure-Monitor-3.png "フィールドの抽出ウィザード")

4. RenderedDescription から抽出し、フィールドのタイトルを提供したいデータを強調表示します。 表 1 には、使用するフィールド名が用意されています。

   ![ユーザー設定フィールドの定義](../../media/Deploy-Azure-Monitor-4.png "ユーザー設定フィールドの定義")

5. *表 1*に示すようにマッピングを使用します。 ログ分析機能が自動的に追加されます、 ** \_CF**文字列の新しいフィールドを定義するとします。

> [!IMPORTANT]
> JSON とログ分析のすべてのフィールドは大文字小文字を区別することを忘れないでください。
> 
> 次の表に各ユーザー設定のフィールドに必要なクエリに注意してください。 ログ分析の適切なクエリを使用して、カスタム フィールドの値を正常に抽出する必要があります。
> 
 ![ユーザー設定フィールドの定義](../../media/Deploy-Azure-Monitor-5.png "ユーザー設定フィールドの定義")

表 1.

| JSON フィールド                   | **ログ分析機能のユーザー設定フィールド** | イベント ID | **抽出に使用するクエリ**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 説明                      | SRSEventDescription         | $2,000     | イベント\|、実際のソース"SRS App"とイベント Id = = = 2000 |
| ResourceState                    | SRSResourceState            | $2,000     | イベント\|、実際のソース"SRS App"とイベント Id = = = 2000 |
| OperationName                    | SRSOperationName            | $2,000     | イベント\|、実際のソース"SRS App"とイベント Id = = = 2000 |
| OperationResult                  | SRSOperationResult          | $2,000     | イベント\|、実際のソース"SRS App"とイベント Id = = = 2000 |
| OS                               | SRSOSVersion                | $2,000     | イベント\|、実際のソース"SRS App"とイベント Id = = = 2000 |
| OSVersion                        | SRSOSLongVersion            | $2,000     | イベント\|、実際のソース"SRS App"とイベント Id = = = 2000 |
| Alias                            | SRSAlias                    | $2,000     | イベント\|、実際のソース"SRS App"とイベント Id = = = 2000 |
| DisplayName                      | SRSDisplayName              | $2,000     | イベント\|、実際のソース"SRS App"とイベント Id = = = 2000 |
| AppVersion                       | SRSAppVersion               | $2,000     | イベント\|、実際のソース"SRS App"とイベント Id = = = 2000 |
| IPv4Address                      | SRSIPv4Address              | $2,000     | イベント\|、実際のソース"SRS App"とイベント Id = = = 2000 |
| IPv6Address                      | SRSIPv6Address              | $2,000     | イベント\|、実際のソース"SRS App"とイベント Id = = = 2000 |
| 会議マイクの状態     | SRSConfMicrophoneStatus     | **3001**     | イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001 |
| 会議の発表者のステータス        | SRSConfSpeakerStatus        | **3001**     | イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001 |
| スピーカーの既定の状態           | SRSDefaultSpeakerStatus     | **3001**     | イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001 |
| カメラの状態                    | SRSCameraStatus             | **3001**     | イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001 |
| ルームの表示状態の前面     | SRSFORDStatus               | **3001**     | イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001 |
| モーション センサーのステータス             | SRSMotionSensorStatus       | **3001**     | イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001 |
| HDMI 取り込みの状態               | SRSHDMIIngestStatus         | **3001**     | イベント\|、実際のソース"SRS App"とイベント Id = = = = の 3001 |


## <a name="define-the-skype-room-systems-v2-views-in-log-analytics"></a>ログ分析で Skype ルーム システム v2 ビューを定義します。
<a name="Define_Views"> </a>

データが収集され、ユーザー設定フィールドがマップされている後、は、Skype ルーム システム v2 のイベントを監視するためのさまざまなタイルを含むダッシュ ボードを開発するのにデザイナーの表示を使用できます。 ビュー デザイナーを使用して、次のファイルを作成します。 詳細については、[ログの分析で、ビュー デザイナーを使用してカスタム ビューを作成する](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)を参照してください。

> [!NOTE]
> 正常に動作するダッシュ ボードのタイルのこのガイドで前の手順への接続が完了する必要があります。

### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a>インポート メソッドを使用して、Skype ルーム システム v2 のダッシュ ボードを作成します。

Skype ルーム システム v2 のダッシュ ボードにインポートし、デバイスを簡単に監視を開始できます。 ダッシュ ボードにインポートするのには以下の手順を実行するには。

1.  [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675)ダッシュ ボード ファイルを取得します。
2.  [Microsoft Azure ポータル](https://portal.azure.com)にサインインし、どうなるログの分析に新しいワークスペースを選択します。
3.  **ビュー デザイナー**を開きます。
4.  **インポート**] を選択し、 **SkypeRoomSystems_v2.omsview**ファイルを選択します。
5.  **保存**を選択します。

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a>Skype ルーム システム v2 のダッシュ ボードを手動で作成します。

または、独自のダッシュ ボードを作成し、監視対象のタイルのみを追加できます。

#### <a name="configure-the-overview-tile"></a>概要タイルを構成します。

1.  **ビュー デザイナー**を開きます。
2.  **概要タイル**を選択し、ギャラリーから**2 つの数値**を選択します。
3.  **Skype ルーム システム v2**のタイルの名前を指定します。
4.  **最初のタイル**を定義します。<br>
    **凡例:** 最後の月以内にハートビートを送信するデバイス<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  **2 つ目のタイル**を定義します。<br>
    **凡例:** 最後の時間内にハートビートを送信するアクティブなデバイス<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  **適用**を選択します。

### <a name="create-a-tile-that-displays-active-devices"></a>アクティブなデバイスを表示するタイルを作成します。

1.  タイルを追加する**ダッシュ ボードのビュー**を選択します。
2.  **_AMP_ リストに番号**を選択して、ギャラリーから
3.  **全般**プロパティを定義します。<br>
    **グループ タイトル:** ハートビートの状態<br>
    **新しいグループ:** 選択
4.  **タイル**のプロパティを定義します。<br>
    **凡例:** アクティブなデバイス (ハートビートの最後の 20 分間で送信されます)<br>
    タイルのクエリ: 
5.  **リスト**のプロパティを定義します。<br>
    リストのクエリ: 
6.  **列のタイトル**を定義します。<br>
    **名:** コンピューター名<br>
    **値:** 最後のハートビート
7.  **ナビゲーション クエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  **適用**され、し、**閉じる**を選択します。

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>接続の問題のあるデバイスを表示するタイルを作成します。

1.  ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。
2.  **全般**プロパティを定義します。<br>
    **グループ タイトル:** 空のままに<br>
    **新しいグループ:** 選択されていません。
3.  **タイル**のプロパティを定義します。<br>
    **凡例:** 非アクティブなデバイス (ハートビート メッセージは最後の 20 分間で送信されます)<br>
    タイルのクエリ: 
4.  **リスト**のプロパティを定義します。<br>
    リストのクエリ: 
5.  **列のタイトル**を定義します。<br>
    **名:** コンピューター名<br>
    **値:** 最後のハートビート
6.  **ナビゲーション クエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  **適用**され、し、**閉じる**を選択します。

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>ハードウェア エラーのあるデバイスを表示するタイルを作成します。

1.  ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。
2.  **全般**プロパティを定義します。<br>
    **グループ タイトル:** ハードウェアのステータス<br>
    **新しいグループ:** 選択
3.  **タイル**のプロパティを定義します。<br>
    **凡例:** 最後の 1 時間以内にハードウェア エラーが発生したデバイス<br>
    タイルのクエリ: 
4.  **リスト**のプロパティを定義します。<br>
    リストのクエリ: 
5.  **列のタイトル**を定義します。<br>
    **名:** コンピューター名<br>
    **値:** 最後のエラー
6.  **ナビゲーション クエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  **適用**され、し、**閉じる**を選択します。

### <a name="create-a-tile-that-displays-skype-room-systems-v2-operating-system-versions"></a>Skype ルーム システム v2 バージョンのオペレーティング システムを表示するタイルを作成します。

1.  ギャラリーから、**ドーナツ & リスト**を選択し、新たにコピーします。
2.  **全般**プロパティを定義します。<br>
    **グループ タイトル:** オペレーティング システムの詳細<br>
    **新しいグループ:** 選択
3.  **ヘッダー**のプロパティを定義します。<br>
    **タイトル:** オペレーティング システムのバージョン<br>
    **サブタイトル:** 特定の OS バージョンを実行しているデバイス
4.  **ドーナツ**のプロパティを定義します。<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **テキストを中央揃え:** デバイス<br>
    **操作:** 合計
5.  **リスト**のプロパティを定義します。<br>
    リストのクエリ: <br>
    **グラフを非表示にする:** 選択<br>
    **スパーク ラインを有効にする:** 選択されていません。
6.  **列のタイトル**を定義します。<br>
    **名:** コンピューター名<br>
    **値:** 空のままに
7.  **ナビゲーション クエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  **適用**し、[**閉じる**を選択します。

### <a name="create-a-tile-that-displays-skype-room-systems-v2-application-versions"></a>Skype ルーム システム v2 のアプリケーションのバージョンを表示するタイルを作成します。

1.  ギャラリーから、**ドーナツ & リスト**を選択し、新たにコピーします。
2.  **全般**プロパティを定義します。<br>
    **グループ タイトル:** Skype ルーム システム v2 のアプリケーションの詳細<br>
    **新しいグループ:** 選択
3.  **ヘッダー**のプロパティを定義します。<br>
    **タイトル:** アプリケーションのバージョン<br>
    **サブタイトル:** 特定のアプリケーションのバージョンを実行しているデバイス
4.  **ドーナツ**のプロパティを定義します。<br>
    **クエリ:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **テキストを中央揃え:** デバイス<br>
    **操作:** 合計
5.  **リスト**のプロパティを定義します。<br>
    リストのクエリ: <br>
    **グラフを非表示にする:** 選択<br>
    **スパーク ラインを有効にする:** 選択されていません。
6.  **列のタイトル**を定義します。<br>
    **名:** コンピューター名<br>
    **値:** 空のままに
7.  **ナビゲーション クエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  **適用**し、[**閉じる**を選択します。

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>アプリケーション エラーのあるデバイスを表示するタイルを作成します。

1.  ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。
2.  **全般**プロパティを定義します。<br>
    **グループ タイトル:** 空のままに<br>
    **新しいグループ:** 選択されていません。
3.  **タイル**のプロパティを定義します。<br>
    **凡例:** 最後の時間でアプリケーション エラーが発生したデバイス<br>
    タイルのクエリ: 
4.  **リスト**のプロパティを定義します。<br>
    リストのクエリ: 
5.  **列のタイトル**を定義します。<br>
    **名:** コンピューター名<br>
    **値:** 最後のエラー
6.  **ナビゲーション クエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  **適用**し、[**閉じる**を選択します。

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>再起動されているデバイスを表示するタイルを作成します。

1.  ギャラリーから、[ **&] ボックスの一覧の番号**を選択し、新しいタイルを追加します。
2.  **全般**プロパティを定義します。<br>
    **グループ タイトル:** 空のままに<br>
    **新しいグループ:** 選択されていません。
3.  **タイル**のプロパティを定義します。<br>
    **凡例:** デバイスのアプリケーションの再起動では、最後の 24 時間、および再起動の回数<br>
    タイルのクエリ: 
4.  **リスト**のプロパティを定義します。<br>
    リストのクエリ: 
5.  **列のタイトル**を定義します。<br>
    **名:** コンピューター名<br>
    **値:** 再起動の回数
6.  **ナビゲーション クエリ**を定義します。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  **適用**し、[**閉じる**を選択します。
8.  ダッシュ ボードを保存する**保存**を選択します。

ここで、ビューの作成が完了しました。

## <a name="configure-alerts-in-azure-monitor"></a>Azure のモニターで警告を構成します。
<a name="Alerts"> </a>

Azure のモニターには、Skype ルーム システム v2 のコンソールに問題が発生した場合、管理者に通知するアラートを発生できます。

Azure のモニターには、定期的にスケジュールされたログの検索を実行する組み込みの警告メカニズムが含まれています。 ログの検索の結果には、いくつか特定の条件が一致する場合は、アラートのレコードが作成されます。

自動的に、ルールでは、事前に警告を通知または別のプロセスを起動する 1 つまたは複数のアクションを実行できるし。 アラートを使用可能なオプションは次のとおりです。
-   電子メールを送信します。
-   HTTP POST 要求を外部プロセスを起動します。
-   Runbook を Azure のオートメーション サービスの開始

Azure モニターの警告に関する詳細については、 [Azure のモニターで警告をログに記録](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log)を参照してください。

> [!NOTE]
> 次の例は、Skype ルーム システム v2 デバイスは、ハードウェアまたはアプリケーション エラーを生成する場合に電子メール警告を送信します。

### <a name="configure-an-email-alert-for-skype-room-systems-v2-hardware-issues"></a>Skype ルーム システム v2 のハードウェアの問題に関する電子メール通知を構成します。

最後の時間内でハードウェアの問題が発生している Skype ルーム システム v2 のデバイスを確認する警告ルールを構成します。
1.  [Microsoft Azure ポータル](https://portal.azure.com)にサインインし、どうなるログの分析に新しいワークスペースを選択します。

2. ログの分析機能のワークスペースに移動し**アラート**を選択し、**新しいアラート ルール**を選択し、

3. [**条件の追加**し、[**カスタム ログの検索**

4.  検索クエリのテキスト ボックスに次のクエリを入力します。<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  警告のロジックの設定を構成します。<br>
    **に基づく:** 結果の数<br>
    **条件:** 大きいし、<br>
    **しきい値:** 0<br>

6. 評価の設定を構成し、**実行**を選択します。 <br>
    **時間 (分単位):** 60<br>
    **頻度 (分):** 60<br>

7. アクションのグループを構成します。
    1.  **新規作成**を選択します。
    2.  *アクション グループの名前*と*短い名前*のフィールドに適切な名前を提供します。
    3.  固有の*アクション名*を指定、**電子メール、SMS、プッシュ/音声**を選択し、[**詳細の編集**] を選択します。
    4.  電子メール] チェック ボックスを選択しのユーザーまたはグループのアラートを受信する電子メール アドレスを提供します。
    5.  SMS、音声通話、またはその両方を使用して通知を受け取るため、電話番号を入力することもできます。
    6. **[Ok]** を選択します。

8. **アクションをカスタマイズする**警告の電子メールの件名行をオーバーライドする場合です。

9. ルールの名前と説明を指定します。<br>
    **ルールの名前:** Skype ルーム システム v2 ハードウェア障害の警告<br>
    **説明:** 最後の時間内でハードウェアの問題が発生したデバイスの一覧<br>

10. 目的の重要度を選択し、ルールが有効になっているかどうかを確認します。

11. **警告ルールを作成**を選択します。

### <a name="configure-an-email-alert-for-skype-room-systems-v2-application-issues"></a>Skype ルーム システム v2 のアプリケーションの問題に関する電子メール通知を構成します。

同じ手順を繰り返しますが、最後の時間内でアプリケーションの問題が発生しているデバイスの一覧表示するには、次のクエリを使用します。

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

警告の定義を完了しました。 上記の例を使用して、別のアラートを定義できます。

アラートが生成されると、最後の時間内で問題が発生しているデバイスを一覧表示する電子メールが表示されます。

![サンプル Azure モニター警告の電子メール](../../media/Deploy-Azure-Monitor-6.png "サンプル Azure モニター警告の電子メール")

## <a name="configure-all-devices-for-azure-monitoring"></a>Azure を監視するためのすべてのデバイスを構成します。
<a name="configure_all_devices"></a>ダッシュ ボード、アラートを構成した後は、設定および監視、展開を完了するすべての Skype ルーム システム v2 デバイスで Microsoft の監視エージェントを構成します。

インストールし、デバイスごとに、Microsoft の監視エージェントを手動で構成できますが、既存のソフトウェア展開ツールおよび方法を活用するを強くお勧めします。

最初に、Skype ルーム システム v2 のデバイスを作成する場合は、ビルド プロセスの一環としてマイクロソフトの監視エージェントのセットアップと構成の手順が含まれます。 詳細については、[コマンド ・ ラインを使用してエージェントのインストール](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)を参照してください。

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>グループ ポリシー オブジェクト (GPO) を使用して、Microsoft の監視エージェントを展開します。

Azure の監視を実装する前に、Skype ルーム システム v2 デバイス既に展開されている場合を設定し、Active Directory グループ ポリシー オブジェクトを使用してエージェントを構成する提供されたスクリプトを使用することができます。

1.  共有のネットワーク パスを作成し、**ドメイン コンピューター**グループに読み取りアクセスを許可します。

2.  監視エージェントの Windows からの 64 ビット バージョンをダウンロードします。<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  ネットワーク共有には、セットアップ パッケージの内容を抽出します。
    1.  コマンド プロンプト ウィンドウを開き、 **MMASetup AMD64.exe/c**を実行し、
    2.  作成した共有を指定し、コンテンツを抽出します。

4.  新しいグループ ポリシー オブジェクトを作成し、Skype ルーム システム v2 のコンピューター アカウントが格納されている組織単位に割り当てます。

5.  PowerShell 実行ポリシーを構成します。
    1.  新しく作成したグループ ポリシー オブジェクトを編集し、コンピューターの構成に移動\\ポリシー\\管理用テンプレート\\Windows コンポーネントの\\Windows PowerShell
    2.  **スクリプトの実行を有効に**するを有効にして、**実行ポリシー**を**ローカルのスクリプトを許可する**に設定します。

6.  スタートアップ ・ スクリプトを構成します。
    1.  次のスクリプトをコピーし、インストールを MMAgent.ps1 として保存します。
    2.  構成に合わせて、WorkspaceId、WorkspaceKey、および SetupPath のパラメーターを変更します。
    3.  同じグループ ポリシー オブジェクトを編集し、コンピューターの構成に移動\\ポリシー \\ Windows の設定\\スクリプト (スタートアップ/シャット ダウン)
    4.  ダブルクリックして**起動**を選択し、 **PowerShell スクリプト**します。
    5.  **ファイルを表示**] を選択し、そのフォルダーに**インストールを MMAgent.ps1**ファイルをコピーします。
    6.  **追加**して、**参照**を選択します。
    7.  コピーした ps1 スクリプトを選択します。

7.  Skype ルーム システム v2 のデバイスがインストールされ、2 つ目の再起動で、Microsoft の監視エージェントを構成します。

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
> エージェントを再構成して、別のワークスペースに移動する、または最初のインストール後にプロキシの設定を変更する必要がある場合は、[エージェント ログの分析機能を維持して管理](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage)の資料を参照できます。

## <a name="additional-solutions"></a>他のソリューション
<a name="Solutions"> </a>

Azure のモニターでは、お客様の環境を監視するため、[ソリューション ギャラリー](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)からの組み込み管理ソリューションを提供します。 ワークスペースには、[警告の管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)と[ログ分析エージェント稼働状態の Azure](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)ソリューションを追加することを強くお勧めします。

> [!NOTE]
> エージェントの正常性のソリューションを使用して、環境内の古いか破損している Microsoft の監視エージェントを特定でき、アラート管理ソリューションには、一定期間内に発生して、アラートに関する詳細情報が用意されています。

## <a name="see-also"></a>関連項目

[Azure のモニターを使用して Skype ルーム システム v2 の管理を計画します。](../../plan-your-deployment/clients-and-devices/azure-monitor.md)

[Azure のモニターを使用して Skype ルーム システム v2 のデバイスを管理します。](../../manage/skype-room-systems-v2/azure-monitor.md)