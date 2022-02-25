---
title: 自動応答 &キュー履歴レポート
author: CarolynRowe
ms.author: crowe
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
description: 通話品質ダッシュボード レポートを使用して、通話Power BI履歴データ自動応答を表示する方法について説明します。
ms.openlocfilehash: bb83a31b083387bc945f7f4b4388ee6643c00f10
ms.sourcegitcommit: eb5fadedacbf4651ed5b05f1b0d6abf57e9eda2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2022
ms.locfileid: "62921875"
---
# <a name="auto-attendant--call-queue-historical-report"></a>自動応答 &キュー履歴レポート

[Teams 自動応答 & Call Queue Historical Report Power BI テンプレートには、次の 3 つのレポートが表示されます。

- [自動応答](media/cqd-teams-aa-cq-historical-report-sample-aa.png) – 自動応答に着信する通話の分析を表示します。
- [通話キュー](media/cqd-teams-aa-cq-historical-report-sample-cq.png) – 通話キューに着信する通話の分析を示します。
- [エージェント タイムライン](media/cqd-teams-aa-cq-historical-report-sample-at.png) – 通話キュー呼び出しでアクティブなエージェントのタイムライン ビューを示します。

これらのレポートでは、通話品質ダッシュボード [データ ストアのデータを](CQD-Power-BI-query-templates.md) 使用します。 このレポートを使用すると、組織は自動応答と通話キューによって処理される通話の数を報告できます。  また、このレポートは、呼び出しキューでのエージェントのパフォーマンスに関する分析情報も提供します。

## <a name="prerequisites"></a>前提条件

### <a name="power-bi-desktop"></a>Power BI Desktop
インストールする必要Power BI Desktopがあります。 Microsoft Windows [Store からインストールできます](https://aka.ms/pbidesktopstore)。

無料版の Power BI Desktop。 互換性のある最小バージョンは 2.85.681.0 (2020 年 9 月) です。

### <a name="permissions-to-access-the-cqd-pipeline"></a>CQD パイプラインにアクセスするためのアクセス許可

履歴レポートを表示するために使用するアカウントには、CQD データ パイプラインにアクセスするためのアクセス許可が必要です。 詳細については、 [CQD アクセス ロールに関するページを参照してください](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

## <a name="installation"></a>インストール 

次の手順では、コンピューターに Power BI Desktop が既にインストールされ、CQD データ パイプラインにアクセスするために必要なアクセス許可がアカウントに付与されていることを前提とします。

次の手順を実行します。

- [CQD クエリ テンプレートPower BIダウンロード](https://www.microsoft.com/download/details.aspx?id=102291)し、zip ファイルをコンピューター上のディレクトリに保存します。

- zip ファイルをダブルクリックして開きます。

- "CQ and AA combined Analytics 20201105.pbit" テンプレート ファイルをダブルクリックします。 このPower BI Desktop起動します。

- CQD データ パイプライン リージョンを選択するように求めるメッセージが表示されます。 テナントがあるリージョンを選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="CQD データ パイプラインリージョンを選択したスクリーンショット。":::

- テナントがあるリージョンは、 [Get-CsTenant コマンドレットを使用して取得](/powershell/module/skype/get-cstenant) できます。

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - リージョンは、上記の例のように **/** の後に表示されます。リージョンは noam です。

 - レポートが起動し、サンプル データが表示されます。
 
 - 独自のデータを表示するには、[クエリ] の [ホーム] タブで [最新の情報に更新] Power BI Desktop。

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="更新オプションを選択したスクリーンショット。":::

- その後、サインインを求めるメッセージが表示されます。 [組織 **アカウント] を選択** し、[ **サインイン] を選択します**。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="ログインを示すスクリーンショット。":::

- [Connect] **を** 選択し、データの更新を確認します。

## <a name="data-latency-and-aa--cq-analytics"></a>データの待機時間と AA & CQ 分析

データは、CQD データ パイプラインで 30 分以内に利用できます。

新しい分析データを表示するには、データを更新する必要があります。 

## <a name="customization"></a>カスタマイズ 

さまざまな視覚エフェクトに表示するフィールドの追加や削除、グラフの種類の変更など、レポートの特定の視覚エフェクトの側面をカスタマイズできます。

レポートにデータ フィールドを追加することはできません。

### <a name="change-color-schema"></a>カラー スキーマを変更する 

次の手順では、インストール手順が既に完了済みである前提で説明します。

次の手順を実行します。
- リボンの **[表示] タブ** を選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="配色を変更する [表示] タブを選択するスクリーンショット。":::

- ドロップダウン リストからカラー スキーマを選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="さまざまな配色を示すスクリーンショット。":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>自動応答と呼び出しキューの履歴レポートの定義

### <a name="cloud-auto-attendant-analytics"></a>Cloud 自動応答 Analytics

#### <a name="report-description"></a>レポートの説明

|レポート セクション                          |説明                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|着信通話ソース <sup>1</sup>        |内部/外部の呼び出し元別の呼び出しの分散             |
|ディレクトリ検索方法の合計          |検索の種類別の呼び出しの分布                               |
|呼び出し元アクション                           |通話受信者別の呼び出しの分散                             |
|呼び出し結果                             |最終的な呼び出し状態別の呼び出しの分布                          |
|呼び出し元のアクション数                     |通話中に使用される番号アクション別の呼び出しの分布        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD テーブルへのレポートとフィールド マッピング

|[レポート] タブ            |レポート テーブル名     |グローバル フィルター                          |
|:---------------------|:---------------------|:--------------------------------------|
|自動応答        |fAutoAttendant        |AAStartTime は過去 28 日以内です |


|レポート テーブル名            |ソース テーブル名            |処理       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Source = AutoAttendant、 <br>#"Filtered Rows" = Table.SelectRows(Source, each true), <br>#"自動応答" = Table.AddColumn(#"Filtered Rows", "AA Name", each List.First(Text.Split([AAIdentity], "@"))) <br>#"Changed Type" = Table.TransformColumnTypes(#"自動応答",{{"AAStartTime", type datetime}}), <br>#"Removed Columns" = Table.RemoveColumns(#"Changed Type",{"AAIdentity"}) |


|レポート セクション                                  |Field(s) Used                              |適用されたフィルター     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|日付セレクター                                   |AAStartTime                                |なし                |
|自動応答                                  |AA 名                                    |なし                |
|着信通話ソース <sup>1</sup>                |通話の種類<br>TotalCallCount                |外部呼び出し: 通話の種類は外部<br>内部呼び出し: 呼び出しの種類は内部です |
|ディレクトリ検索方法の合計                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod がabs_search_dtmfまたはabs_search_name    |
|呼び出し元のアクション                                  |AATransferAction<br>TotalCallCount         |なし                                                             |
|AA の平均秒<br>呼び出し元アクションの平均 |AAChainDuration<br>AACallerActionCount     |なし                                                             |
|結果を呼び出す                                    |AACallResult<br>TotalCallCount             |なし                                                             |
|呼び出し元のアクション数                            |AACallerActionCount<br>TotalCallCount      |なし                                                             |
|レポートの下部                         |AA 名<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>通話の種類<br>TotalCallCount |なし                |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD フィールドの説明

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名                                 |テキスト                     |リソース にアタッチされているリソース アカウント自動応答<br><br>完全なリソース アカウント名が指定されている **aa_test@microsoft.com** 、この値は次の値 **aa_test** |
|AACallerActionCount                     |数値を指定します。             |要約: 合計<br>通話中に呼び出し元によって自動応答されたアクションの数  |
|AACallFlow                              |テキスト                     |呼び出しの異なる状態自動応答可能な値をカプセル化します。<br><br>§ abs_search<br>§ announcement<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |テキスト                     |最終的な呼び出し結果 -- 指定可能な値:<br><br>§ failed_to_establish_media<br>§ failover_to_operator<br>§ oaa_chain_too_long<br>§ oaa_session_too_long<br>§ service_declined<br>§ service_terminated<br>§ terminated_automatic_selection<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>***§ transferred_to_operator***<br>§ transferred_to_receptionist<br>§ transferred_to_self<br>§ transferred_to_shared_voicemail<br>§ transferred_to_user<br>§ unknown<br>§ user_terminated |
|AAChainDuration                         |10 進数           |要約: 合計<br>通話時間 (自動応答                     |
|AAChainIndex                            |テキスト                     |                                                                         |
|AAConnectivityType                      |テキスト                     |呼び出しの種類 -- 指定可能な値:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |テキスト                     |通話に関係する自動応答の数                               |
|AADirectorySearchMethod                 |テキスト                     |最後のアドレス帳の検索方法 -- 指定可能な値:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |日付/時刻                |自動応答開始時刻                                           |
|AATransferAction                        |テキスト                     |呼び出し転送ターゲットの種類 -- 指定可能な値:<br><br>***§ application - voice application entity**_<br>§ external_pstn§ hunt_group<br>_ *_- Call Queue entity_*_<br>_*_§ orgaa - organizational 自動応答 entity_**<br>§ shared_voicemail<br>§ unknown<br>§ user |
|通話の種類 <sup>1</sup>                   |テキスト                     |呼び出しの種類 -- 指定可能な値:<br><br>§ External<br>§ Internal         |
|IsAAInvolved                            |テキスト                     |常に 1                                                                 |
|PSTNMinutes                             |数値を指定します。             |要約: 合計<br>分の合計使用量                                     |
|TotalCallCount                          |数値を指定します。             |要約: 合計<br>Always 1 - すべての呼び出しの合計を提供するために使用されます。            |


### <a name="cloud-call-queue-analytics"></a>Cloud Call Queue Analytics

#### <a name="report-description"></a>レポートの説明

|レポート セクション                          |説明                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|着信通話ソース <sup>1</sup>        |内部/外部の呼び出し元による呼び出しの分散              |
|通話ボリューム                             |呼び出しキュー別の呼び出しの分散                                |
|呼び出し元の結果                           |呼び出し結果別の呼び出しの分布                                |
|Timeout/Overflow 呼び出しの合計アクション      |呼び出し結果による NOT forwarded(abandoned) 呼び出しの分布       |
|転送/転送ターゲットの合計          |呼び出し結果によって転送された呼び出しの分布                      |
|破棄された呼び出しの比率                   |破棄された呼び出し数に対する成功の比率                        |
|平均セッション長 (秒)        |呼び出しの長さ (秒) を破棄/成功した呼び出しでグループ化       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD テーブルへのレポートとフィールド マッピング

|[レポート] タブ         |レポート テーブル名                                                          |グローバル フィルター |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|通話キュー         |日付<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |なし          |
 
|レポート テーブル名            |ソース テーブル名            |処理       |
|:----------------------------|:----------------------------|:----------------|
|日付                        |日付                        |なし             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics, <br>#"Removed Columns" = Table.RemoveColumns(Source,{"Call Count", "Call Queue Call Result", "Date", "PSTN Connectivity Type", "Call Queue Target Type", "PSTN Total Minutes"}),<br>Distinct = Table.Distinct(#"Removed Columns") |
|fCallQueueAnalytics          |CallQueueAnalytics           |なし             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |なし             |

|レポート セクション                      |Table -> フィールドの使用                |適用されたフィルター       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日付セレクター                       |Dates -> DateTime                     |なし                  |
|キュー ID の呼び出し                 |dCQ-CQIdentity -> 呼び出しキュー ID |なし                  |
|着信通話ソース <sup>1</sup>    |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> 呼び出しの種類    |外部呼び出し: 通話の種類は外部<br>内部呼び出し: 呼び出しの種類は内部です |
|平均待機時間                    |fCallQueueFinalStateAction ->平均呼び出し時間 (秒) |転送前: 通話キュー呼び出しの結果がagent_joined_conferenceまたはtransferred_to_agent<br>電話を切る前: 通話キュー呼び出しの結果がagent_joined_conferenceまたはtransferred_to_agent |
|呼び出し結果                         |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Call Queue Call Result | なし |
|Timeout/Overflow 呼び出しの合計アクション |fCallQueueFinalStateAction -> Call Count<br>fCallQueueFinalStateAction -> Call Queue Final State Action |呼び出しキューの最終状態アクションが転送されない |
|転送/Forard ターゲットの合計       |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Call Queue Target Type |なし |
|通話ボリューム                        |fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Call Queue Identify<br>fCallQueueAnalytics -> Date |なし |
|破棄された呼び出し                     |fCallQueueAnalytics -> %Abandoned Calls<br>fCallQueueAnalytics -> Call Count<br>fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned は True です |
|平均セッション長 (秒)    |fCallQueueFinalStateAction ->平均呼び出し時間<br>fCallQueueFinalStateAction -> Date<br>fCallQueueFinalStateAction -> IsAbandoned |なし |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>dCQ-CQIdenity CQD フィールドの説明

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|キュー ID の呼び出し                     |テキスト                     |通話キューに接続されているリソース アカウントの名前<br><br>完全なリソース アカウント名が指定されている **cq_test@microsoft.com** 、この値は次 **の値cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD フィールドの説明

|名前                                    |データ型                |説明                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|通話数                              |数値を指定します。             |要約: 合計<br>通話の数                                          |
|キュー呼び出しの結果を呼び出す                  |テキスト                     |呼び出しキュー呼び出しの最終状態 -- 可能な値:<br><br>§ agent_joined_conference<br>§ declined<br>§ disconnected<br>§ error<br>§ failed<br>§ invalid<br>§ overflown<br>§ timed_out<br>§ transferred_to_agent |
|キュー ID の呼び出し                     |テキスト                     |通話キューに接続されているリソース アカウントの名前<br><br>完全なリソース アカウント名が指定されている **cq_test@microsoft.com** 、この値は次 **の値cq_test** |
|呼び出しキュー ターゲットの種類                  |テキスト                     |***呼び出しリダイレクトターゲットの種類 -- 可能な値:***<br><br>§ ApplicationEndpoint<br>§ Mailbox<br>§ Other<br>§ User |
|通話の種類 <sup>1</sup>                   |テキスト                     |呼び出しの種類 -- 指定可能な値:<br><br>§ External<br>§ Internal           |
|日付                                    |日付/時刻                |通話キュー呼び出しの開始日時 (時間) (UTC)                           | 
|IsAbandoned                             |True/false               |エージェントが呼び出しに応答しない場合は true                                   |
|PSTN 接続の種類                  |テキスト                     |呼び出しの種類 -- 指定可能な値:<br><br>§ ExternalCall<br>§ InternalCall   |
|PSTN の合計時間 (分)                      |数値を指定します。             |要約: 合計<br>PSTN 通話の合計通話時間 (分)                       |

#### <a name="fcallqueueanalytics-measures-description"></a>fCallQueueAnalytics メジャーの説明

|名前                                    |データ型                |説明                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***通話の破棄率***                 |パーセンテージ               |メジャー: 破棄された呼び出しの数/通話の合計    |
|合計通話数                             |数値を指定します。             |測定: エージェントの応答呼び出しの合計        |
|TotalCallCount                          |数値を指定します。             |メジャー: Sum(呼び出し回数)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction CQD フィールドの説明

|名前                                    |データ型                |説明                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|平均通話時間 (秒)         |10 進数           |要約: 合計<br>平均通話時間 (秒) |
|通話数                              |数値を指定します。             |要約: 合計<br>通話の数                  |
|キュー呼び出しの結果を呼び出す                  |テキスト                     |呼び出しキュー呼び出しの最終状態 -- 可能な値:<br><br>§ agent_joined_conference<br>§ declined<br>§ disconnected<br>§ error<br>§ failed<br>§ invalid<br>§ overflown<br>§ timed_out<br>§ transferred_to_agent |
|呼び出しキューの最終状態アクション           |テキスト                     |呼び出しキューの最終的なアクション -- 可能な値:<br><br>§ disconnect (timed_out 呼び出し)<br>§ disconnect_with_busy (オーバーフローした呼び出し)<br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ other<br>§ ボイスメール |
|キュー ID の呼び出し                     |テキスト                     |通話キューに接続されているリソース アカウントの名前<br><br>完全なリソース アカウント名が指定されている **cq_test@microsoft.com** 、この値は次 **の値cq_test** |
|日付                                    |日付/時刻                |通話キュー呼び出しの開始日時 (時間) (UTC)   |
|IsAbandoned                             |True/false               |エージェントが呼び出しに応答しない場合は true           |


### <a name="cloud-call-queue-agent-timeline"></a>クラウド呼び出しキュー エージェントのタイムライン

#### <a name="report-description"></a>レポートの説明

|レポート セクション                                          |説明                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|エージェントによる # 呼び出し                                        |呼び出しキューとエージェントによる呼び出しの分散                 |
|エージェントと通話キュー別の合計通話時間 (秒)   |エージェントと呼び出しキュー別の呼び出しの合計時間 (秒)     |
|エージェント名別の平均呼び出し時間 (秒)           |エージェント別の呼び出しの平均継続時間 (秒)                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD テーブルへのレポートとフィールド マッピング

|[レポート] タブ         |レポート テーブル名        |グローバル フィルター |
|:------------------|:-------------------------|:-------------|
|エージェントタイムライン     |fAgentTimelineAnalytics   |なし          |
 
|レポート テーブル名            |ソース テーブル名            |処理       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics, <br>#"Changed Type" = Table.TransformColumnTypes(Source,{{"Call Count", Int64.Type}, {"Call Duration (Minute)", Int64.Type}, {"Average Call Duration (Second)", type number}, {"Date", type date}})|

|レポート セクション                                |Field(s) Used                         |適用されたフィルター       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|エージェント名                                    |エージェント名                            |なし                  |
|通話キュー名                               |通話キュー名                       |なし                  |
|#Callsエージェント別                               |エージェント名<br>通話数<br>日付      |なし                  |
|エージェントと呼び出しキュー別の配布          |エージェント名<br>通話数<br>通話時間 (分)<br>通話キュー名 |なし                      |
|左下                                   |エージェント名<br>平均通話時間 (秒)<br>通話数<br>通話時間 (分)<br>通話キュー名 | なし |
|エージェント名別の平均通話時間 (秒) |エージェント名<br>平均通話時間 (秒)<br>通話数<br>通話時間 (分)<br>通話キュー名 | なし |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD フィールドの説明

|名前                                    |データ型                |説明                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|エージェント名                              |テキスト                     |User UPN<br>完全なユーザー名が有効 **user@microsoft.com** 、次の値は **user になります。** |
|平均通話時間 (秒)          |10 進数           |要約: 合計<br>通話キュー呼び出しの平均継続時間 (秒) |
|通話数                              |数値を指定します。             |要約: 合計<br>エージェントによって処理される呼び出しの数                    |
|通話時間 (分)                  |数値を指定します。             |要約: 合計<br>通話キュー呼び出しの合計通話時間 (分単位)  |
|通話キュー名                         |テキスト                     |通話キューに接続されているリソース アカウントの名前<br><br>完全なリソース アカウント名が指定されている **cq_test@microsoft.com** 、この値は次 **の値cq_test** |
|日付                                    |日付                     |                                                    |


> [!NOTE]
> 1) このレポートは、エージェントの観点から見た通話数を示します。そのため、このレポートの呼び出し回数の合計は、通常、 **Cloud Call Queue Analytics** レポートの呼び出しの総数よりも多くなります。 キュー内の各呼び出しは、応答する前に少なくとも 1 回は 1 つ以上のエージェントに表示できます。 エージェントに対して提示された呼び出しキューの呼び出しは、エージェントによって応答されなくても、このレポートでカウントされます。 これら 2 つのレポートの呼び出し回数の違いは、すべての呼び出しに対してすべてのエージェントを呼び出す **ア** テンダント ルーティング オプションの方が顕著です。 
> 2) 呼び出しが最初の呼び出しキューに最初に到着すると、そのキューで既に待機している呼び出しの数が呼び出しオーバーフロー処理の制限を超えた場合、リダイレクト オプションが 2 番目の呼び出しキューに呼び出しを送信した場合、2 番目の呼び出しキュー内のエージェントは、このレポートの最初の呼び出しキューにあると表示されます。 

## <a name="known-issues"></a>既知の問題

- 通話キューと自動応答は、呼び出しキュー/自動応答名ではなく、リソース アカウントの ID によって表示されます。  自動応答または通話キューのすべてのトラフィックを表示するには、自動応答または通話キューに割り当てられているすべてのリソース アカウントを選択する必要があります。

- 通話キュー/自動応答データは個人データと見なされ、データプライバシー保持ポリシーの対象となるので、ダッシュボードで使用できる履歴は 28 日間のみです。

- シナリオによっては、エージェントが Cloud Call Queue Agent Timeline レポートの呼び出し回数に応答した場合、クライアントの通話履歴に表示される呼び出しの数Teams異なる場合があります。 クライアントTeamsの呼び出し履歴が正しい。 サポートは調査中ですが、現時点では修復できる予定時間はありません。

- <sup>1</sup> **自動応答の着信通話ソース** と通話キュー グラフには、初期呼び出しの読み取り元ではなく、最終的な通話の読み取り元が表示されます。 たとえば、自動応答が外部通話を受信し、その通話を別の自動応答または通話キューに転送した場合、着信通話ソースは内部として報告されます。
