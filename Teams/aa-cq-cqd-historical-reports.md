---
title: 自動応答と通話キューの履歴レポートを更新しました
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: 更新された Teams 自動応答&通話キュー履歴レポート Power BI レポートを使用して、自動応答と通話キューの履歴データを表示する方法について説明します。
ms.openlocfilehash: ed267cf2d96f15236aa68339049d2c721249ec00
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763558"
---
# <a name="auto-attendant-and-call-queue-historical-reports"></a>自動応答と通話キューの履歴レポート

>[!NOTE]
> GCC HIgh と DOD のお客様は、引き続き自動応答の V1.63 [&通話キュー履歴レポート (CQD)](aa-cq-cqd-historical-reports-v163.md) を使用する必要があります。

この Power BI テンプレートには、組織が自動応答と呼び出しキューによって処理されている通話の数を報告できる 3 つのレポートが用意されています。  また、エージェントのパフォーマンスに関する分析情報も提供します。

## <a name="v305-published-on-january-9-2023"></a>2023 年 1 月 9 日に公開された V3.0.5

Teams 自動応答&通話キュー履歴レポート Power BI テンプレートには、次の 3 つのレポートが用意されています。

- [自動応答](media/aa-cq-historical-report-sample-aa-v305.png)レポートには、自動応答に着信する通話の分析が表示されます。
- 通話キュー レポートには、 [通話キュー](media/aa-cq-historical-report-sample-cq-v305.png) に入ってくる通話の分析が表示されます。
- [エージェント タイムライン](media/aa-cq-historical-report-sample-at-v305.png) レポートには、通話キュー呼び出しでアクティブになっているエージェントのタイムライン ビューが表示されます。

これらのレポートでは、Voice Applications Analytics Collector (VAAC) サービスのデータが使用されます。

## <a name="v3xx-prerequisites"></a>V3.x.x の前提条件

### <a name="power-bi-desktop"></a>Power BI Desktop

Power BI Desktopをインストールする必要があります。 [Microsoft Windows ストア](https://aka.ms/pbidesktopstore)から無料版をインストールして使用できます。

互換性のある最小バージョンは 2.85.681.0 (2020 年 9 月) です。

### <a name="permissions-to-access-the-cqd-pipeline"></a>CQD パイプラインにアクセスするためのアクセス許可

このバージョンのレポートでは通話品質ダッシュボード (CQD) データ パイプラインは使用されませんが、履歴データの表示に使用されるアカウントには通話品質ダッシュボードへのアクセスが必要です。 詳細については、「 [CQD アクセス ロール](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)」を参照してください。

**[レポートの表示]** フィールドと [**EUII の表示] フィールド** の両方が **[はい**] に設定されている CQD ロールは機能します。

- この要件は、今後のリリースで削除される予定です。

## <a name="v3xx-installation"></a>V3.x.x のインストール 

次の手順では、コンピューターにPower BI Desktopが既にインストールされていることと、アカウントに CQD データ パイプラインにアクセスするために必要なアクセス許可があることを前提としています。

次の手順を実行します。

1. [Teams 自動応答&通話キュー履歴レポート V3.0.5.zip](https://www.microsoft.com/download/details.aspx?id=104623) ファイルをコンピューターにダウンロードして保存します。

2. zip ファイルを開きます。

3. テンプレート ファイルを `Teams Auto Attendant & Call Queue Historical Reports V3.0.5.pbit` 開きます。 Power BI Desktopが起動します。

4. **データ ソース** を選択するように求められます。  エントリを `api.interfaces.records.teams.microsoft.com` 選択します。

  :::image type="content" source="media/aa-cq-historical-report-01-v305.png" alt-text="api.interfaces.records.teams.microsoft.com Data Soure を選択するスクリーンショット":::

5. アカウントでサインインするように求められます。 [ **組織アカウント**] を選択し、[サインイン] を選択 **します**。

  :::image type="content" source="media/aa-cq-historical-report-03-v300.png" alt-text="V3.0.0 のログインを示すスクリーンショット。":::

6. [ **接続**] を選択すると、データが更新されます。

> [!NOTE]
> v1.63 以前を使用していた場合、v3.x.x が VAAC からデータを取得しようとしたときにエラーが発生する可能性があります。  このエラーを解決するには、以前の資格情報を Power BI からクリアする必要があります。
> 
> 1. v3.x.x テンプレートを開いてエラーをクリアします。 
> 1. [**ファイル** > **オプション] & [設定]****[データ ソース設定]** >  の順に選択します。
> 1. [ **アクセス許可のクリア**] ドロップダウンを選択し、[ **すべてのアクセス許可のクリア**] を選択します。
> 1. テンプレートがクリアされたら閉じ、Power BI を再起動します。 もう一度承認するように求められます。 

## <a name="data-latency-for-auto-attendant-and-call-queue-analytics"></a>自動応答と通話キュー分析のデータ待機時間

通常、データは通話が完了してから 30 分以内に使用できます。ただし、データが表示されるまでに数時間かかる場合があります。 

新しいデータを表示するには、データを更新する必要があります。

## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>自動応答と通話キューの履歴レポートの定義

### <a name="cloud-auto-attendant-analytics-report"></a>クラウド自動応答分析レポート

#### <a name="report-description"></a>レポートの説明

|レポート セクション                          |説明                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|着信呼び出し元                    |内部/外部呼び出し元による呼び出しの分散            |
|ディレクトリ検索方法                 |検索の種類別の呼び出しの分布                              |
|呼び出し元アクション数                     |通話中に使用される番号アクション別の呼び出しの分布       |
|AA の平均秒数                   |呼び出し元が AA で費やす平均秒数                 |
|呼び出し元の平均アクション                  |呼び出し元が AA で実行する平均アクション数               |
|結果の呼び出し                            |最終呼び出し状態による呼び出しの分散                         |
|レポートの下位セクション                 |通話フローの内訳                                               |

#### <a name="report-visual-and-field-mapping"></a>ビジュアルとフィールドのマッピングをレポートする

|[レポート] タブ            |レポート テーブル名     |グローバル フィルター                          |
|:---------------------|:---------------------|:--------------------------------------|
|自動応答        |fAutoAttendant        |なし                                   |

|レポート セクション                               |使用されるフィールド                                                                                    |適用されたフィルター |
|:--------------------------------------------|:------------------------------------------------------------------------------------------------|:----------|
|日付セレクター                                |AAStartTime                                                                                      |なし       |
|時間範囲セレクター                          |AAStartHour                                                                                      |なし       |
|自動応答リソース アカウント             |AA 名                                                                                          |なし       |
|着信呼び出し元                         |通話の種類<br>TotalCallCount の合計         |外部呼び出し: 呼び出しの種類は外部<br>内部呼び出し: 呼び出しの種類は内部 |
|ディレクトリ検索方法                      |AADirectorySearchMethod<br>AADirectorySearchMethodLegend<br>TotalCallCount  |AADirectorySearchMethod がabs_search_dtmfまたはabs_search_name    |
|呼び出し元アクション数                          |AACallerActionCount<br>TotalCallCount                                                            |なし       |
|AA の平均秒数                        |AAChainDuration                                                                                  |なし       |
|呼び出し元の平均アクション                       |AACallerActionCount                                                                              |なし       |
|結果の呼び出し                                 |AACallResult<br>AACallResultLegend<br>TotalCallCount                                             |なし       |
|レポートの下位セクション                      |MM-DD<br>AA 名<br>AACallFlow<br>通話の種類<br>AACallResult<br>TotalCallCount<br>AAChainDuration |なし       |

#### <a name="fautoattendant-field-description"></a>fAutoAttendant フィールドの説明

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名                                 |テキスト                     |自動応答にアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **aa_test@microsoft.com** されている場合、この値は **aa_test** |
|AA 開始時刻 UTC                       |日付/時刻                |自動応答通話の開始時刻 - UTC                                                     |
|AACallerActionCount                     |整数             |要約: 合計<br>通話中に自動応答で呼び出し元によって選択されたアクションの数  |
|AACallerActionCount (Measure)           |整数             |AACallerActionCount と同じですが、空白ではなく呼び出しがない場合は 0 になります。                |
|AACallFlow                              |テキスト                     |自動応答ディメンション -> AutoAttendantCallFlow に関するページを参照してください                                   |
|AACallResult                            |テキスト                     |「自動応答ディメンション -> AutoAttendantCallResult」を参照してください                                 |
|AACallResultLegend                      |テキスト                     |AACallResult に基づいて凡例項目を設定する                                               |
|AAChainDuration                         |10 進数           |要約: 合計<br>自動応答での通話時間                                     |
|AAChainDuration (メジャー)               |10 進数           |AAChainDuration と同じですが、空白ではなく呼び出しがない場合は 0 になります。                    |
|AAChainIndex                            |整数             |                                                                                         |
|AAConnectivityType                      |テキスト                     |「一般的なディメンション -> PSTNConnectivityType」を参照してください                                            |
|AACount                                 |整数             |通話に関係する自動応答の数                                               |
|AADirectorySearchMethod                 |テキスト                     |「自動応答ディメンション -> AutoAttendantDirectorySearchMethod」を参照してください                      |
|AADirectorySearchMethodLegend           |テキスト                     |AADirectorySearchMethod に基づいて凡例項目を設定します                                    |
|AAStartHour                             |整数             |自動応答通話の開始時刻                                                           |
|AAStartTime                             |日付/時刻                |自動応答呼び出しの開始時刻                                                           |
|AATransferAction                        |テキスト                     |「自動応答ディメンション -> AutoAttendantTransferAction」を参照してください                             |
|通話時間 (秒)                   |整数             |通話時間                                                                            |
|通話終了時刻ローカル                     |日付/時刻                |通話の終了時刻 - ローカル (レポートを実行しているコンピューターのタイム ゾーンに基づく)                    |
|終了時刻 UTC を呼び出す                       |日付/時刻                |通話の終了時刻 - UTC                                                                      |
|通話開始時刻ローカル                   |日付/時刻                |通話開始時刻 - ローカル (レポートを実行しているコンピューターのタイム ゾーンに基づく)                  |
|開始時刻 UTC を呼び出す                     |日付/時刻                |通話開始時刻 - UTC                                                                    |
|通話の種類<sup>1</sup>                   |テキスト                     |「共通ディメンション -> PSTNCallType」を参照してください                                                    |
|ConferenceID                            |テキスト                     |トラブルシューティングのために使用 - チケットを開くときにこの情報を提供する       |
|DialogID                                |テキスト                     |トラブルシューティングのために使用 - チケットを開くときにこの情報を提供する       |
|DocumentID                              |テキスト                     |トラブルシューティングのために使用 - チケットを開くときにこの情報を提供する       |
|MM-DD                                   |テキスト                     |自動応答通話の月日                                                            |
|PSTNMinutes                             |整数             |要約: 合計<br>合計分使用量                                                     |
|TotalCallCount の合計 (メジャー)         |整数             |TotalCallCount と同じですが、空白ではなく呼び出しがない場合は 0 になります                     |
|TotalCallCount                          |整数             |要約: 合計<br>Always 1 - すべての呼び出しの合計を提供するために使用されます                            |


### <a name="cloud-call-queue-analytics-report"></a>Cloud Call Queue Analytics レポート

#### <a name="report-description"></a>レポートの説明

|レポート セクション                          |説明                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|着信呼び出し元                    |内部/外部呼び出し元による呼び出しの分散             |
|平均待機時間 (秒)             |応答された呼び出しと破棄された呼び出しの待機時間                         |
|通話量とエージェントのオプトイン数      |呼び出しキュー別の呼び出しの分散/ エージェントオプトインの最大数  |
|結果の呼び出し                            |呼び出し結果による呼び出しの分散                               |
|破棄された呼び出し                         |呼び出しキューによる破棄された呼び出しの分散                     |
|平均セッション長 (秒)        |呼び出し結果でグループ化された通話の長さ (秒単位)                      |
|呼び出しのオーバーフロー/タイムアウトの宛先      |タイムアウトまたはオーバーフローした呼び出しの分散                 |


#### <a name="report-visual-and-field-mapping"></a>ビジュアルとフィールドのマッピングをレポートする

|[レポート] タブ            |レポート テーブル名                                   |グローバル フィルター       |
|:---------------------|:---------------------------------------------------|:-------------------|
|通話キュー            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |なし                |

|レポート セクション                      |テーブル -> フィールドの使用                |適用されたフィルター       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日付セレクター                       |fCallQueueAnalytics -> Date           |なし                  |
|時間範囲セレクター                 |fCallQueueAnalytics -> CQHour         |なし                  |
|キュー リソース アカウントの呼び出し         |fCallQueueAnalytics -> CQ 名        |なし                  |
|着信呼び出し元                |fCallQueueAnalytics ->呼び出し回数の合計 (メジャー)  |外部呼び出し: 呼び出しの種類は外部<br>内部呼び出し: 呼び出しの種類は内部 |
|平均待機時間 (秒)-回答前 |fCallQueueFinalStateAction -> 平均 CQ 期間の平均 (メジャー) |通話キュー呼び出し結果がagent_joined_conferenceまたはtransferred_to_agent|
|平均待機時間 (秒)-破棄前 |fCallQueueFinalStateAction -> 平均通話時間の平均 (メジャー) |通話キュー呼び出し結果がagent_joined_conference、transferred_to_agent、オーバーフロー、timed_out |
|通話ボリュームとエージェントのOpt-In数   |fCallQueueAnalytics -> 呼び出し数<br>fCallQueueAnalytics -> 通話キュー エージェントオプトインカウント<br>fCallQueueAnalytics -> CQ 名<br>fCallQueueAnalytics -> Date |なし |
|破棄された呼び出し                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | 呼び出しキュー呼び出し結果の凡例が破棄されました |
|平均セッション長 (秒)    |fCallQueueFinalStateAction ->平均通話キュー期間 (秒)<br>通話キュー呼び出しの結果の凡例 |平均通話キュー期間 (秒) > 0 |
|呼び出しのオーバーフロー/タイムアウトの宛先  |fCallQueueAnalytics -> 呼び出し数<br>fCallQueueAnalytics -> 呼び出しキューターゲットの種類<br>fCallQueue ターゲット型の凡例 |呼び出しキューのターゲットの種類の凡例に破棄済みとエージェント応答が含まれていない |


#### <a name="fcallqueueanalytics-field-description"></a>fCallQueueAnalytics フィールドの説明

|名前                                    |データ型                |説明                                                                              |
|:---------------------------------------|:------------------------|:----------------------------------------------------------------------------------------|
|通話数                              |整数             |要約: 合計<br>通話の数                                                        |
|通話時間 (秒)                   |整数             |通話時間                                                                            |
|通話終了時刻ローカル                     |日付/時刻                |通話の終了時刻 - ローカル (レポートを実行しているコンピューターのタイム ゾーンに基づく)                    |
|終了時刻 UTC を呼び出す                       |日付/時刻                |通話の終了時刻 - UTC                                                                      |
|キュー エージェントの呼び出し数                  |整数             |要約: 合計<br>呼び出しキューに構成されているエージェントの数                          |
|通話キュー エージェントオプトイン数           |整数             |要約: 合計<br>呼び出しキューにオプトインされたエージェントの数                            |
|通話キューの呼び出し結果                  |テキスト                     |「Call Queue Dimensions -> CallQueueCallResult」を参照してください                                         |
|通話キュー呼び出しの結果の凡例           |テキスト                     |通話キューの結果に基づいて凡例項目を設定する                                          |
|キュー ターゲットの種類を呼び出す                  |テキスト                     |「Call Queue Dimensions -> CallQueueTargetType」を参照してください                                         |
|呼び出しキュー ターゲットの種類の凡例           |テキスト                     |通話キュー ターゲットの種類に基づいて凡例項目を設定する                                     |
|通話開始時刻ローカル                   |日付/時刻                |通話開始時刻 - ローカル (レポートを実行しているコンピューターのタイム ゾーンに基づく)                  |
|開始時刻 UTC を呼び出す                     |日付/時刻                |通話開始時刻 - UTC                                                                    |
|通話の種類                               |テキスト                     |「共通ディメンション -> PSTNCallType」を参照してください                                                    |
|ConferenceID                            |テキスト                     |トラブルシューティングのために使用 - チケットを開くときにこの情報を提供する       |
|CQ 名                                 |テキスト                     |通話キューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **cq_test** |
|CQ 時間                                 |整数             |通話キュー呼び出し開始時間                                                               |
|日付                                    |日付/時刻                |通話キュー呼び出しの開始時刻 (時間)                                               | 
|DateTimeCQName                          |テキスト                     |fCallQueueFinalStateAction でフィルター処理するための一意のキー                                   |
|DialogID                                |テキスト                     |トラブルシューティングのために使用 - チケットを開くときにこの情報を提供する       |
|DocumentID                              |テキスト                     |トラブルシューティングのために使用 - チケットを開くときにこの情報を提供する       |
|PSTN 接続の種類                  |テキスト                     |「共通ディメンション -> PSTNConnectivityType」を参照してください                                            |
|PSTN 合計分数                      |整数             |要約: 合計<br>PSTN 通話の合計使用量 (分)                                     |
|通話数の合計 (メジャー)             |整数             |呼び出し数と同じですが、呼び出しがない場合は 0 になります                                        |
|TotalCallCount (Measure)                |整数             |要約: 合計<br>通話数                                                             |


#### <a name="fcallqueuefinalstateaction-field-description"></a>fCallQueueFinalStateAction フィールドの説明

|名前                                    |データ型                |説明                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|平均通話時間 (秒)         |10 進数           |要約: 合計<br>破棄された呼び出しの平均通話時間 (秒単位)     |
|平均通話キュー期間 (秒)       |10 進数           |要約: 合計<br>応答された呼び出しの平均待機時間 (秒単位)       |
|平均通話時間の平均 (測定)  |整数             |平均通話時間 (秒) と同じですが、呼び出しがない場合は 0 になります    |
|平均 CQ 期間の平均 (メジャー)    |整数             |平均通話キュー期間 (秒) と同じですが、呼び出しがない場合は 0 になります  |
|通話数                              |整数             |要約: 合計<br>通話の数                                          |
|通話キューの呼び出し結果                  |テキスト                     |「Call Queue Dimensions -> CallQueueCallResult」を参照してください                           |
|通話キュー呼び出しの結果の凡例           |テキスト                     |通話キューの呼び出し結果に基づいて凡例項目を設定します                       |
|キューの最終状態アクションを呼び出す           |テキスト                     |「Call Queue Dimensions -> CallQueueFinaleStateAction」を参照してください。                    |
|CQ 名                                 |テキスト                     |通話キューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **cq_test** |
|CQ 時間                                 |数値                   |通話が行われた時間
|日付                                    |日付/時刻                |通話キュー呼び出しの開始時刻 (時間)                                 |
|DateTimeCQName                          |テキスト                     |fCallQueueFinalStateAction でフィルター処理するための一意のキー                     |
|IsAbandoned                             |True/false               |呼び出しがエージェントによって応答されない場合は True                                    |


### <a name="cloud-call-queue-agent-timeline-report"></a>クラウド通話キュー エージェントのタイムライン レポート

#### <a name="report-description"></a>レポートの説明

|レポート セクション                                          |説明                                                         |
|:-------------------------------------------------------|:-------------------------------------------------------------------|
|エージェント別の呼び出し数                                |呼び出しキューとエージェントによる呼び出しの分散                       |
|エージェントとすべてのキューによる配布                     |エージェントと呼び出しキューによる呼び出しの分散                       |
|テーブル (左下)                                     |平均通話時間と合計通話時間を持つエージェント別の呼び出しの分布 |
|エージェントごとの平均通話時間 (秒) (右下) |エージェントごとの呼び出しの平均所要時間 (秒)                         |

#### <a name="report-visual-field-mapping"></a>レポートビジュアルフィールドマッピング

|[レポート] タブ            |レポート テーブル名           |グローバル フィルター       |
|:---------------------|:---------------------------|:-------------------|
|エージェントタイムライン        |fAgentTimelineAnalytics     |なし                |


|レポート セクション                                |使用されるフィールド                         |適用されたフィルター       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|日付セレクター                                 |Datetime                              |なし                  |
|エージェントのユーザー名セレクター                       |エージェント名                            |なし                  |
|キュー リソース アカウント セレクターを呼び出す         |CQ 名                               |なし                  |
|エージェント別の呼び出し数                      |通話数<br>エージェント名<br>日付<br>Hour      |なし                  |
|エージェントと呼び出しキュー別の配布          |エージェント名<br>平均通話時間 (秒)<br>通話数<br>CQ 名 |なし                      |
|左下                                   |エージェント名<br>平均通話時間 (秒)<br>通話数<br>通話時間 (分)<br>CQ 名<br>Hour<br>MM-DD | なし |
|エージェント別の平均通話時間 (秒)      |エージェント名<br>平均通話時間 (秒) | なし |

#### <a name="fagenttimelineanalytics-field-description"></a>fAgentTimelineAnalytics フィールドの説明

|名前                                    |データ型                |説明                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|エージェント名                              |テキスト                     |ユーザー UPN<br>完全なユーザー名が **user@microsoft.com** されている場合、この値は **user** になります。 |
|平均通話時間 (秒)         |10 進数           |要約: 合計<br>応答された呼び出しキュー呼び出しの平均時間 (秒単位) |
|通話時間 (分)                 |整数             |要約: 合計<br>応答された通話キュー呼び出しの合計通話時間 (分単位) (切り捨てて最も近い分)  |
|応答された呼び出し                          |整数             |エージェントが応答した呼び出しの数                        |
|応答されない呼び出し                      |整数             |エージェントが応答しない呼び出しの数                    |
|CQ 名                                 |テキスト                     |通話キューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **cq_test** |
|日付                                    |日付                     |通話日                                             |
|Datetime                                |Datetime                 |通話日                                             |
|Hour                                    |整数             |通話時間                                             |
|MM-DD                                   |テキスト                     |通話の月と日                                    |
|合計通話数                        |整数             |要約: 合計<br>エージェントに提示された呼び出しの数     |

> [!NOTE]
> 呼び出しが最初の呼び出しキューに到着すると、そのキューで既に待機している呼び出しの数が **呼び出しオーバーフロー処理** の制限に達し、リダイレクト オプションが 2 番目の呼び出しキューに新しい呼び出しを送信した場合、2 番目の呼び出しキュー内のエージェントはこのレポートの最初の呼び出しキューに含まれていると表示されます。 

## <a name="known-issues"></a>既知の問題

- 通話キューと自動応答は、呼び出しキュー/自動応答名ではなく、リソース アカウントの ID によって表示されます。  自動応答または通話キューのすべてのトラフィックを表示するには、自動応答または通話キューに割り当てられているすべてのリソース アカウントを選択する必要があります。

- 通話キュー/自動応答データは個人データと見なされ、データプライバシー保持ポリシーの対象であるため、ダッシュボードでは 28 日間の履歴のみを使用できます。

- 一部のシナリオでは、 **クラウド通話キュー エージェント タイムライン** レポートのエージェント応答通話数が、Teams クライアントの通話履歴に表示される呼び出しの数と異なる場合があります。 Teams クライアントの通話履歴は正しいです。 サポートは調査中ですが、現時点では修復可能な推定時間はありません。

## <a name="customization"></a>カスタマイズ 

さまざまな視覚化に表示するフィールドの追加や削除、グラフの種類の変更など、レポートの特定の視覚化の側面をカスタマイズできます。

### <a name="change-color-schema"></a>色スキーマを変更する 

次の手順では、インストール手順が既に完了していることを前提としています。

次の手順を実行します。

1. リボンの **[表示] タブ** を選択します。

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="配色を変更する [ビュー] タブを選択しているスクリーンショット。":::

2. ドロップダウン リストからカラー スキーマを選択します。

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="さまざまな配色を示すスクリーンショット。":::
  
## <a name="dimensions-and-measurements"></a>寸法と測定値

使用できる寸法と測定値は次のとおりです。

### <a name="common-dimensions"></a>一般的なディメンション

これらのディメンションは、自動応答と通話キューの両方に共通です。

|名前 (型)                                            |使用可能な値                |説明                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|ConferenceId<br>(テキスト)                                 |GUID                           |呼び出し識別子                                                   |
|日付<br>(DateTime)                                     |                               |通話日 (UTC)                                                |
|DialogId<br>(テキスト)                                     |GUID                           |呼び出し識別子                                                   |
|DocumentId<br>(テキスト)                                   |GUID                           |呼び出し識別子                                                   |
|[時間]<br>(整数)                             |                               |通話時間 (秒単位)                                      |
|EndTime<br>(DateTime)                                  |                               |時間呼び出しが終了しました (UTC)                                             |
|FirstIsCaller<br>(Boolean)                             |                               |[1 番目と 2 番目のエンドポイント分類](dimensions-and-measures-available-in-call-quality-dashboard.md)     |
|FirstUPN<br>(テキスト)                                     |                               |最初のエンドポイントのユーザーのユーザー プリンシパル名 (UPN)        |
|Hour<br>(テキスト)                                         |                               |時間呼び出しの開始 (UTC)                                           |
|Minute<br>(テキスト)                                       |                               |分呼び出しが開始されました (UTC)                                         |
|PSTNCallDuration<br>(整数)                     |                               |通話の時間                                              |
|PSTNCallType<br>(テキスト)                                 |                               |                                                                  |
|                                                       |外部                       |テナントの外部からの呼び出し                            |
|                                                       |内部                       |テナント内からの呼び出し                             |
|PSTNConnectivityType<sup>1</sup><br>(テキスト)             |                               |                                                                  |
|                                                       |CallingPlan                    |                                                                  |
|                                                       |DirectRouting                  |                                                                  |
|2 番目<br>(テキスト)                                       |                               |2 回目の呼び出しが開始されました (UTC)                                         |
|SecondUPN<br>(テキスト)                                    |                               |2 番目のエンドポイントのユーザーのユーザー プリンシパル名 (UPN)       |
|TenantId<br>(テキスト)                                     |                               |テナント ID                                                         |
|タイムスタンプ<br>(DateTime)                                |                               |時刻レコードが書き込まれた (UTC)                                     |
|UserStartTimeUTC<br>(DateTime)                         |                               |呼び出しが開始された時刻 (UTC)                                           |

- <sup>1</sup> **PSTNConnectivityType** は、最初のコール レッグ ソースではなく、最終的なコール レッグ ソースを表示します。 たとえば、自動応答が外部呼び出しを受信し、別の自動応答または通話キューに通話を転送する場合、 **着信呼び出し元** は **内部** として報告されます。


### <a name="auto-attendant-dimensions"></a>自動応答ディメンション

|名前 (型)                                            |使用可能な値                |説明                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AutoAttendantCallFlow<br>(テキスト)                        |                               |自動応答呼び出しのさまざまな状態をカプセル化します          |
|                                                       |abs_search                     |                                                                  |
|                                                       |発表                   |                                                                  |
|                                                       |automatic_menu                 |                                                                  |
|                                                       |call_termination               |                                                                  |
|                                                       |call_transfer                  |                                                                  |
|                                                       |first_level_menu               |                                                                  |
|                                                       |main_menu                      |                                                                  |
|                                                       |speech_input_confirmation      |                                                                  |
|                                                       |user_selection                 |                                                                  |
|AutoAttendantCallResult<br>(テキスト)                      |                               |最終的な呼び出し結果                                                 |
|                                                       |failed_to_establish_media      |通話のメディア部分を確立できませんでした             |
|                                                       |failover_to_operator           |通常、システム エラーが原因でオペレーターに転送される呼び出し      |
|                                                       |oaa_chain_too_long             |AA の足が多すぎます                                           |
|                                                       |oaa_session_too_long           |AA セッションが長すぎる                                    |
|                                                       |service_declined               |AA が呼び出しを受け入れませんでした                                         |
|                                                       |service_terminated             |AA 構成によって通話が切断されるか、通話がハングアップする             |
|                                                       |terminated_automatic_selection |AA 構成によって呼び出しが切断される                           |
|                                                       |terminated_no_operator         |演算子が定義されていないエラーが原因ですべて終了しました                   |
|                                                       |terminated_transfer_failed     |転送に失敗した場合に終了した呼び出し - 通常は外部番号に |
|                                                       |transfer_in_progress           |AA->AA 転送                                                   |
|                                                       |transferred_to_operator        |呼び出しがオペレーターに転送されました                                  |
|                                                       |transferred_to_cq              |呼び出しが呼び出しキューに転送されました                                |
|                                                       |transferred_to_receptionist    |transferred_to_operatorと同じ                                   |
|                                                       |transferred_to_self            |AA の開始時に呼び出しが返されました                          |
|                                                       |transferred_to_shared_voicemail |通話が共有ボイスメールに転送されました                         |
|                                                       |transferred_to_user            |呼び出しがユーザーに転送されました                                    |
|                                                       |未知                        |不明な条件が発生しました                                 |
|                                                       |user_terminated                |呼び出し元がハングアップしました                                                    |
|AutoAttendantCallerActionCounts<br>(整数)      |                               |                                                                  |
|AutoAttendantChainDurationInSecs<br>(実数)      |                               |                                                                  |
|AutoAttendantChainIndex<br>(整数)              |                               |                                                                  |
|AutoAttendantChainStartTime<br>(DateTime)              |                               |                                                                  |
|AutoAttendantCount<br>(整数)                   |                               |                                                                  |
|AutoAttendantDirectorySearchMethod<br>(テキスト)           |                               |ディレクトリ検索方法                                           |
|                                                       |abs_search_dtmf                |タッチトーン                                                        |
|                                                       |abs_search_voice               |音声                                                             |
|AutoAttendantIdentity<br>(テキスト)                        |                               |リソース アカウント URI 呼び出しが到着しました                              |
|AutoAttendantTransferAction<br>(テキスト)                  |                               |通話転送ターゲットの種類                                         |
|                                                       |Aa                             |AA に転送される                                              |
|                                                       |Cq                             |CQ に転送される                                               |
|                                                       |external_pstn                  |外部番号に転送される                                 |
|                                                       |共有ボイスメール               |共有ボイスメールに転送される                                   |
|                                                       |未知                        |不明なアクション                                                    |
|HasAA<br>(Boolean)                                     |                               |呼び出しに AA が関与している                                            |


### <a name="call-queue-dimensions"></a>呼び出しキューディメンション

|名前 (型)                                            |使用可能な値                |説明                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|CallQueueAgentCount<br>(整数)                  |                               |通話キュー内のエージェントの数                                    |
|CallQueueAgentOptInCount<br>(整数)             |                               |キューを呼び出すためにオプトインされたエージェントの数                           |
|CallQueueCallResult<br>(テキスト)                          |                               |通話キュー呼び出しの最終状態                                       |
|                                                       |agent_joined_conference        |通話応答 - 会議モード CQ                                |
|                                                       |減少                       |                                                                  |
|                                                       |切断                   |                                                                  |
|                                                       |error                          |                                                                  |
|                                                       |失敗 しました                         |                                                                  |
|                                                       |無効です                        |                                                                  |
|                                                       |overflown                      |オーバーフロー条件が満たされました                                            |
|                                                       |timed_out                      |タイムアウト条件が満たされました                                             |
|                                                       |transferred_to_agent           |応答された通話 - 転送モード CQ                                  |
|CallQueueDurationSeconds<br>(実数)              |                               |通話キューの通話時間                                   |
|CallQueueFinaleStateAction<br>(テキスト)                   |                               |キューの最終アクションを呼び出す                                           |
|                                                       |切断                     |time_out呼び出し                                                    |
|                                                       |disconnect_with_busy           |overflown 呼び出し                                                   |
|                                                       |failed_to_accept_call          |                                                                  |
|                                                       |転送                        |呼び出しがユーザーまたは外部に転送されました                        |
|                                                       |shared_voicemail               |通話が共有ボイスメールに送信されました                                 |
|                                                       |他                          |                                                                  |
|                                                       |ボイスメール                      |                                                                  |
|CallQueueIdentity<br>(テキスト)                            |                               |リソース アカウント URI 呼び出しが到着しました                              |
|CallQueueTargetType<br>(テキスト)                          |                               |呼び出しリダイレクト ターゲット                                           |
|                                                       |ApplicationEndpoint            |                                                                  |
|                                                       |メールボックス                        |                                                                  |
|                                                       |Other (その他)                          |                                                                  |
|                                                       |電話                          |                                                                  |
|                                                       |ユーザー                           |                                                                  |
|HasCQ<br>(Boolean)                                     |                               |呼び出しに CQ が関与している                                            |
|TransferredFromCallQueueIdentity<br>(テキスト)             |                               |                                                                  |

### <a name="measurements"></a>測定

|名前 (型)                                            |使用可能な値                |説明                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AvgAutoAttendantChainDurationSeconds<br>(実数)  |                               |                                                                  |
|AvgCallDuration<br>(実数)                       |                               |                                                                  |
|AvgCallQueueDurationSeconds<br>(実数)           |                               |                                                                  |
|PSTNTotalMinutes<br>(実数)                      |                               |                                                                  |
|TotalAudioStreamDuration<br>(実数)              |                               |                                                                  |
|TotalCallCount<br>(整数)                       |                               |                                                                  |

### <a name="constructing-a-valid-query"></a>有効なクエリの構築

有効なクエリは、JSON オブジェクト内のいくつかの属性で構成されます。

```json
{
   "Filters":[
      {
         "DataModelName":"Date",
         "Value":"2022-04-01",
         "Operand":4
      },
      {
         "DataModelName":"Date",
         "Value":"2022-04-30",
         "Operand":6
      }
   ],
   "Dimensions":[
      {
         "DataModelName":"AutoAttendantIdentity"
      },
      {
         "DataModelName":"AutoAttendantDirectorySearchMethod"
      }
   ],
   "Measurements":[
      {
         "DataModelName":"PSTNTotalMinutes"
      },
      {
         "DataModelName":"TotalCallCount"
      }
   ],
   "Parameters":{
      "UserAgent":"Power BI Desktop"
   },
   "LimitResultRowsCount":100000
}
```

#### <a name="required-fields"></a>必須フィールド

- フィルター: VAAC によって返されるデータをフィルター処理するために使用されます
- - DataModelName は、サポートされているディメンションのいずれかである必要があります
- - 値は正しい形式 (datetime、string、number など) である必要があります。
- - オペランド：
- - - 0 - 等しい
- - - 1 - 等しくない
- - - 2 - を含む
- - - 3 - で始まる
- - - 4 - より大きい
- - - 5 - 以上
- - - 6 - より小さい
- - - 7 - 以下
- - - 8 - が含まれていません
- - - 9 - で始まらない

- 寸法：
- - DataModelName は、サポートされているディメンションのいずれかである必要があります

- 測定：
- - DataModelName は、サポートされている測定値のいずれかである必要があります

- パラメーター: 現在、UserAgent のみがサポートされています。

- LimitResultRowsCount: VAAC によって返される行の最大数

## <a name="accessing-vaac-outside-of-power-bi"></a>Power BI の外部での VAAC へのアクセス

VAAC API には、RESTful アプリケーションにアクセスできる任意のアプリケーションからアクセスできます。  次の例では、 [Postman](https://www.postman.com/) が使用されます。

### <a name="preparation"></a>準備

[Postman](https://www.postman.com/) をダウンロードします。

リポジトリ [sync_pstn_avs-analytics](https://skype.visualstudio.com/SBS/_git/sync_pstn_avs-analytics) をダウンロードし、解凍します。

フォルダーを Postman にインポートします。 

:::image type="content" source="media/aa-cq-historical-report-postman-01.png" alt-text="インポートが完了したことを示すスクリーンショット":::

### <a name="accessing-vaac-using-postman"></a>Postman を使用した VAAC へのアクセス

1. 右上の [**_環境なし_**] ドロップダウンで [**VAAC - msit**] を選択します。
2. 左側のレール メニューで [ **環境** ] を選択します。
3. [グローバル] で [ **VAAC - msit** ] **を選択します**。
4. **userName**、**password**、**tenantId を** 該当する資格情報に置き換えます。
5. 右上隅にある [ **すべてリセット** ] をクリックします。
6. **[保存]** をクリックします。

:::image type="content" source="media/aa-cq-historical-report-postman-02.png" alt-text="ユーザー名、パスワード、テナント ID フィールドが構成されていることを示すスクリーンショット":::


7. 左側 **の** レール メニューの [コレクション] を選択します。
8. [ **Config API Access Token - Prod** ] を選択し、[ **本文** ] タブに移動します。
9. [ **送信**] をクリックします。

アクセス トークンが返されます。

:::image type="content" source="media/aa-cq-historical-report-postman-03.png" alt-text="アクセス トークンが返された結果を示すスクリーンショット":::

アクセス トークンが返されない場合は、資格情報を確認して、 [十分なアクセス許可](#permissions-to-access-the-cqd-pipeline)を持っているかどうかを確認します。

10. [ **VAAC ConfigAPI Prod] を** 選択し、[ **パラメーター** ] タブに移動します。

- 次に示すようにクエリを[圧縮](#compress-the-json-query)します
- 次に示すように、圧縮された結果を [URL でエンコード](#url-encode-the-compressed-json-query)します

11. [クエリ](#constructing-a-valid-query)文字列を入力します。
12. [ **送信**] をクリックします。

### <a name="reading-the-result"></a>結果の読み取り

入力を送信すると、いくつかの結果が得られます。

- 入力が無効な場合は、実際の理由を示すエラー メッセージが返されます
- 入力が有効な場合、結果は次のようになります。

:::image type="content" source="media/aa-cq-historical-report-postman-04.png" alt-text="dataResult フィールドを使用したクエリ結果を示すスクリーンショット":::

この場合、データは、クエリ ディメンションと測定属性で要求された順序と同じ順序の "dataResult" フィールドに格納されます。


### <a name="compress-the-json-query"></a>JSON クエリを圧縮する

VAAC API は、GZip 圧縮または Base64 でエンコードされた文字列のみを入力として受け入れます。

GZIP または Base64 を使用して JSON BLOB を圧縮する Web サイトを検索します。

- GZIP: (https://www.multiutil.com/text-to-gzip-compress/)
- Base64: (https://www.multiutil.com/text-to-base64-converter/)

GZIP 出力は次のようになります。
````
H4sIAAAAAAAACq2SQWsCMRCF7/6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif+9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf+xJLIGhIo12CjXKPM0o+2cLn2BjEjKVZQM1Gqjhhfy+QQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3/hUBqPKya/WyD41bpCXpP+tzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa/Y2Tk/wI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA=
````

Base64 出力は次のようになります。
````
ew==
IkZpbHRlcnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0wMSIs
Ik9wZXJhbmQiOjQ=
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0zMCIs
Ik9wZXJhbmQiOjY=
fQ==
XSw=
IkRpbWVuc2lvbnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg==
fQ==
XSw=
Ik1lYXN1cmVtZW50cyI6Ww==
ew==
IkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg==
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI=
fQ==
XSw=
IlBhcmFtZXRlcnMiOns=
IlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai
fSw=
IkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA=
fQ==
````

### <a name="url-encode-the-compressed-json-query"></a>圧縮された JSON クエリをURL-Encodeする

GZIP または Base64 圧縮 JSON クエリは [URL エンコード](https://meyerweb.com/eric/tools/dencoder/)されている必要があります。

GZIP URL でエンコードされた出力は次のようになります。
````
H4sIAAAAAAAACq2SQWsCMRCF7%2F6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif%2B9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf%2BxJLIGhIo12CjXKPM0o%2B2cLn2BjEjKVZQM1Gqjhhfy%2BQQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3%2FhUBqPKya%2FWyD41bpCXpP%2BtzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa%2FY2Tk%2FwI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA%3D
````

Base64 URL でエンコードされた出力は次のようになります。
````
%0Aew%3D%3D%0AIkZpbHRlcnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0wMSIs%0AIk9wZXJhbmQiOjQ%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0zMCIs%0AIk9wZXJhbmQiOjY%3D%0AfQ%3D%3D%0AXSw%3D%0AIkRpbWVuc2lvbnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg%3D%3D%0AfQ%3D%3D%0AXSw%3D%0AIk1lYXN1cmVtZW50cyI6Ww%3D%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg%3D%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI%3D%0AfQ%3D%3D%0AXSw%3D%0AIlBhcmFtZXRlcnMiOns%3D%0AIlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai%0AfSw%3D%0AIkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA%3D%0AfQ%3D%3D
````

## <a name="version-3xx-history"></a>バージョン 3.x.x の履歴

変更の詳細な一覧については、「Teams 自動応答&通話キューの履歴レポート - ダウンロードした zip ファイルのLog.docxを変更する」を参照してください。 

|バージョン  |発行日     |Filename                                                    |説明                                                             |
|:--------|:------------------|:-----------------------------------------------------------|:-----------------------------------------------------------------------|
|3.0.5    |2023 年 1 月 9 日    |Teams 自動応答&通話キュー履歴レポート V3.0.5 |呼び出しオーバーフロー/タイムアウトの宛先とエージェント タイムラインのビジュアルの改善  |
|3.0.4    |2022 年 11 月 18 日  |Teams 自動応答&通話キュー履歴レポート V3.0.4 |エラーの修正、呼び出し分類の改善、凡例の追加             |
|3.0.3    |2022 年 11 月 8 日   |Teams 自動応答&通話キュー履歴レポート V3.0.3 |エラーの修正、ドキュメント リンクの追加、最適化されたクエリ            |
|3.0.1    |2022 年 10 月 26 日   |Teams 自動応答&通話キュー履歴レポート V3.0.1 |テスト データ ソースエントリを削除しました                                       |
|3.0.0    |2022 年 10 月 25 日   |Teams 自動応答&通話キュー履歴レポート V3.0.0 |新しいバックエンド データ ソース                                                 |
