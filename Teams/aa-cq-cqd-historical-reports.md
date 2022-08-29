---
title: 自動応答&通話キュー履歴レポート
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
description: 通話品質ダッシュボード Power BI レポートを使用して、自動応答と通話キューの履歴データを表示する方法について説明します。
ms.openlocfilehash: ec345a66a06b03bb9926ff74ceac7b85b31a0190
ms.sourcegitcommit: 850038f2248c1ea412f7b5daca26c0598baffa3c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2022
ms.locfileid: "67443344"
---
# <a name="auto-attendant--call-queue-historical-report"></a>自動応答&通話キュー履歴レポート

Teams 自動応答&通話キュー履歴レポート Power BI テンプレートには、次の 3 つのレポートがあります。

- [自動応答 – 自動応答](media/cqd-teams-aa-cq-historical-report-sample-aa.png) に着信する呼び出しの分析を示します。
- [通話キュー – 通話キュー](media/cqd-teams-aa-cq-historical-report-sample-cq.png) に着信する通話の分析を示します。
- [エージェント タイムライン](media/cqd-teams-aa-cq-historical-report-sample-at.png) – 通話キューの呼び出しでアクティブになっているエージェントのタイムライン ビューを示します。

これらのレポートでは、 [通話品質ダッシュボード](CQD-Power-BI-query-templates.md) データ ストアのデータが使用されます。 このレポートを使用すると、組織は自動応答と通話キューによって処理される通話の数を報告できます。  また、レポートは、呼び出しキュー内のエージェントのパフォーマンスに関する分析情報も提供します。

### <a name="v163-published-on-august-24-2022"></a>2022 年 8 月 24 日に公開された V1.63

## <a name="prerequisites"></a>前提条件

### <a name="power-bi-desktop"></a>Power BI Desktop
Power BI Desktopがインストールされている必要があります。 [Microsoft Windows ストア](https://aka.ms/pbidesktopstore)からインストールできます。

無料版のPower BI Desktopを使用できます。 互換性のある最小バージョンは 2.85.681.0 (2020 年 9 月) です。

### <a name="permissions-to-access-the-cqd-pipeline"></a>CQD パイプラインにアクセスするためのアクセス許可

履歴レポートを表示するために使用するアカウントには、CQD データ パイプラインにアクセスするためのアクセス許可が必要です。 詳細については、「 [CQD アクセス ロール](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)」を参照してください。

## <a name="installation"></a>インストール 

次の手順では、コンピューターにPower BI Desktopが既にインストールされていること、およびアカウントに CQD データ パイプラインにアクセスするために必要なアクセス許可があることを前提としています。

次の手順を実行します。

- [CQD Power BI クエリ テンプレート](https://www.microsoft.com/download/details.aspx?id=102291)をダウンロードし、zip ファイルをコンピューターのディレクトリに保存します。

- zip ファイルをダブルクリックして開きます。

- "CQD Teams 自動応答&通話キュー履歴レポート V1.60.pbit" テンプレート ファイルをダブルクリックします。 Power BI Desktopが起動する必要があります。

- CQD データ パイプラインリージョンを選択するように求められます。 テナントが配置されているリージョンを選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="CQD データ パイプラインリージョンを選択するスクリーンショット。":::

- テナントが配置されているリージョンは、 [Get-CsTenant](/powershell/module/skype/get-cstenant) コマンドレットを使用して取得できます。

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - リージョンは、上記の例のように次のように後に表示されます **/** 。リージョンは次のようになります。

 - サンプル データを使用してレポートが起動します。
 
 - 独自のデータを表示するには、Power BI Desktopの [クエリ] の [ホーム] タブで [**更新**] を選択します。

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="更新オプションを選択するスクリーンショット。":::

- サインインするように求められます。 **[組織アカウント]** を選択し、[**サインイン**] を選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="ログインを示すスクリーンショット。":::

- [ **接続** ] を選択し、データ更新を確認します。

## <a name="data-latency-and-aa--cq-analytics"></a>データ待機時間と AA & CQ 分析

データは通常、通話が完了してから 30 分以内に利用できます。ただし、データが表示されるまでに数時間かかる場合があります。 

新しいデータを表示するには、データを更新する必要があります。

## <a name="customization"></a>カスタマイズ 

さまざまな視覚化に表示されるフィールドの追加や削除、グラフの種類の変更など、レポートの特定の視覚化の側面をカスタマイズできます。

レポートには、現在使用可能なすべてのデータ メトリックが含まれています。

### <a name="change-color-schema"></a>カラー スキーマを変更する 

次の手順は、インストール手順が既に完了していることを前提としています。

次の手順を実行します。
- リボンの **[表示] タブ** を選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="[ビュー] タブを選択して配色を変更するスクリーンショット。":::

- ドロップダウン リストからカラー スキーマを選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="さまざまな配色を示すスクリーンショット。":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>自動応答と呼び出しキュー履歴レポートの定義

### <a name="cloud-auto-attendant-analytics"></a>Cloud Auto Attendant Analytics

#### <a name="report-description"></a>レポートの説明

|[レポート] セクション                          |説明                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|着信呼び出し元<sup>1</sup>        |内部/外部の呼び出し元による呼び出しの配布            |
|ディレクトリ検索メソッド                 |検索の種類別の呼び出しの分布                              |
|呼び出し元のアクション数                     |通話中に使用される番号アクションによる通話の分散       |
|AA の平均秒数                   |呼び出し元が AA で費やす平均秒数                 |
|呼び出し元の平均アクション                  |AA で呼び出し元が実行するアクションの平均数               |
|結果の呼び出し                            |最終呼び出し状態による呼び出しの分布                         |
|レポートの下部セクション                 |通話フローの内訳                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD テーブルとフィールド マッピングへのレポート

|[レポート] タブ            |レポート テーブル名     |ソース テーブル名            |グローバル フィルター                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|自動応答        |fAutoAttendant        |AutoAttendant                |なし                                   |

|[レポート] セクション                                  |使用されるフィールド                              |適用されたフィルター     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|日付セレクター                                   |AAStartTime                                |なし                |
|時間範囲セレクター                             |AAStartHour                                |なし                |
|自動応答                                  |AA 名                                    |なし                |
|着信呼び出し元<sup>1</sup>                |通話の種類<br>TotalCallCount の合計 (Measure) |外部呼び出し: 呼び出しの種類は外部です<br>内部呼び出し: 呼び出しの種類は内部です |
|ディレクトリ検索メソッド                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod がabs_search_dtmfまたはabs_search_name    |
|呼び出し元のアクション数                             |AACallerActionCount<br>TotalCallCount      |なし                                                             |
|AA の平均秒数                           |AAChainDuration (Measure)                  |なし                                                             |
|呼び出し元の平均アクション                          |AACallerActionCount (Measure)              |なし                                                             |
|結果の呼び出し                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |なし                                       |
|レポートの下部セクション                         |AA 名<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>通話の種類<br>MM-DD<br>TotalCallCount |なし       |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD フィールドの説明

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名                                 |テキスト                     |自動応答にアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **aa_test@microsoft.com** されている場合、この値は **次のようになります:aa_test** |
|AACallerActionCount                     |整数             |要約: 合計<br>通話中に自動応答で呼び出し元によって選択されたアクションの数  |
|AACallerActionCount (Measure)          |整数             |空ではなく呼び出しがない場合は 0 になる場合を除き、上記と同じ                              |
|AACallFlow                              |テキスト                     |自動応答呼び出し可能な値のさまざまな状態をカプセル化します。<br><br>§ abs_search<br>§ お知らせ<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |テキスト                     |最終的な呼び出しの結果-可能な値:<br><br>§ failed_to_establish_media (通話のメディア部分を確立できませんでした)<br>§ failover_to_operator (通常はシステム エラーが原因でオペレーターに転送される呼び出し)<br>§ oaa_chain_too_long (AA で足が多すぎます)<br>§ oaa_session_too_long (AA セッションが長すぎます)<br>§ service_declined (AA が呼び出しを受け入れませんでした)<br>§ service_terminated (AA 構成で通話が切断されるか、通話がハングアップ)<br>§ terminated_automatic_selection (AA 構成は呼び出しを切断します)<br>§ terminated_no_operator (エラーが原因で呼び出しが終了し、演算子が定義されていません) <br>§ terminated_transfer_failed (転送に失敗して終了した呼び出し - 通常は外部番号)<br>§ transfer_in_progress (AA->AA 転送)<br>§ transferred_to_operator (呼び出しはオペレーターに転送されました 。通常はユーザー エラーが原因)<br>§ transferred_to_receptionist (transferred_to_operatorと同じ)<br>§ transferred_to_self (呼び出しは AA の先頭に返されました 。通常はメニューのお知らせオプションから)<br>§ transferred_to_shared_voicemail (通話が共有ボイスメールに転送されました)<br>§ transferred_to_user (通話がユーザーに転送された - 通話キューを含む)<br>§ unknown (不明な状態が発生しました)<br>§ user_terminated (発信者がハングアップ) |
|AA 呼び出しの凡例                          |テキスト                     |AACallResult に基づいて凡例項目を設定する                               |
|AAChainDuration                         |10 進数           |要約: 合計<br>自動応答での呼び出しの継続時間                     |
|AAChainDuration (Measure)               |10 進数           |空ではなく呼び出しがない場合は 0 になる場合を除き、上記と同じ              |
|AAChainIndex                            |テキスト                     |                                                                         |
|AAConnectivityType                      |テキスト                     |呼び出し可能な値の種類:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |テキスト                     |通話に関連する自動応答の数                               |
|AADirectorySearchMethod                 |テキスト                     |最後のアドレス帳検索方法 - 可能な値:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |10 進数           |自動応答通話の開始時間                                           |
|AAStartTime                             |日付/時刻                |自動応答呼び出しの開始時刻                                           |
|AATransferAction                        |テキスト                     |転送先の種類の呼び出し可能な値:<br><br>§ アプリケーション - 音声アプリケーション エンティティ<br>§ external_pstn<br>§ hunt_group - キュー エンティティの呼び出し<br>§ orgaa - 自動応答エンティティ<br>§ shared_voicemail<br>§ 不明<br>§ ユーザー |
|呼び出しの種類<sup>1</sup>                   |テキスト                     |呼び出し可能な値の種類:<br><br>§ 外部<br>§ 内部           |
|IsAAInvolved                            |テキスト                     |常に 1                                                                 |
|MM-DD                                   |テキスト                     |自動応答呼び出しの月日                                            |
|PSTNMinutes                             |整数             |要約: 合計<br>合計分の使用量                                     |
|TotalCallCount                          |整数             |要約: 合計<br>常に 1 - すべての呼び出しの合計を提供するために使用されます            |
|TotalCallCount の合計 (Measure)         |整数             |空ではなく呼び出しがない場合は 0 になる場合を除き、上記と同じ              |


### <a name="cloud-call-queue-analytics"></a>Cloud Call Queue Analytics

#### <a name="report-description"></a>レポートの説明

|[レポート] セクション                          |説明                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|着信呼び出し元<sup>1</sup>        |内部/外部の呼び出し元による呼び出しの配布             |
|平均待機時間 (秒)             |応答呼び出しと破棄された呼び出しの待機時間                          |
|通話ボリュームとエージェントオプトイン数      |呼び出しキュー別の呼び出しの分布 / エージェントオプトインの最大数  |
|結果の呼び出し                            |呼び出し結果による呼び出しの分布                               |
|破棄された呼び出し                         |呼び出しキューによる破棄された呼び出しの分散                     |
|平均セッション長 (秒)        |呼び出し結果別にグループ化された呼び出しの長さ (秒単位)                      |
|コール オーバーフロー/タイムアウトの宛先      |タイムアウトまたはオーバーフローした呼び出しの分布                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD テーブルとフィールド マッピングへのレポート

|[レポート] タブ            |レポート テーブル名                                   |ソース テーブル名                               |グローバル フィルター       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|キューの呼び出し            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |なし                |

|[レポート] セクション                      |使用されるテーブル -> フィールド                |適用されたフィルター       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日付セレクター                       |fCallQueueAnalytics -> Date           |なし                  |
|時間範囲セレクター                 |fCallQueueAnalytics -> CQHour         |なし                  |
|キュー リソース アカウントの呼び出し         |fCallQueueAnalytics -> CQ 名        |なし                  |
|着信元<sup>1</sup>    |fCallQueueAnalytics -> 通話数の合計 (Measure)<br>fCallQueueAnalytics ->呼び出しの種類    |外部呼び出し: 呼び出しの種類は外部です<br>内部呼び出し: 呼び出しの種類は内部です |
|平均待機時間 (秒)-応答前 |fCallQueueFinalStateAction -> 平均 CQ 期間の平均平均 (メジャー) |呼び出しキュー呼び出し結果がagent_joined_conferenceまたはtransferred_to_agent|
|平均待機時間 (秒)-破棄される前 |fCallQueueFinalStateAction -> 平均通話時間の平均 (メジャー) |呼び出しキュー呼び出し結果がagent_joined_conference、transferred_to_agent、オーバーフロー、timed_out |
|通話ボリュームとエージェントのOpt-In数   |fCallQueueAnalytics ->呼び出し数<br>fCallQueueAnalytics -> 通話キュー エージェントオプトイン数<br>fCallQueueAnalytics -> CQ 名<br>fCallQueueAnalytics -> Date |なし |
|破棄された呼び出し                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | Call Queue Call Result Legend is Abandoned |
|平均セッション長 (秒)    |fCallQueueFinalStateAction ->呼び出しキューの平均期間 (秒)<br>呼び出しキュー呼び出し結果の凡例 |平均通話キュー期間 (秒) > 0 |
|コール オーバーフロー/タイムアウトの宛先  |fCallQueueAnalytics ->呼び出し数<br>fCallQueueAnalytics -> 呼び出しキュー ターゲットの種類<br>fCallQueue ターゲット型の凡例 |呼び出しキュー ターゲットの種類の凡例に破棄済みとエージェント応答が含まれていない |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD フィールドの説明

|名前                                    |データ型                |説明                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|通話数                              |整数             |要約: 合計<br>通話の数                                          |
|キュー エージェントの呼び出し数                  |整数             |要約: 合計<br>呼び出しキューに構成されているエージェントの数            |
|通話キュー エージェントオプトイン数           |整数             |要約: 合計<br>通話キューにオプトインしたエージェントの数              |
|呼び出しキュー呼び出しの結果                  |テキスト                     |呼び出しキュー呼び出しの最終的な状態 -可能な値:<br><br>§ agent_joined_conference (応答済みの電話会議モードの呼び出し)<br>§ 拒否済み<br>§ 切断済み<br>§ エラー<br>§ 失敗しました<br>§ 無効<br>§ overflown (オーバーフロー条件が満たされました)<br>§ timed_out (タイムアウト条件が満たされている)<br>§ transferred_to_agent (応答転送モード呼び出し {default}) |
|呼び出しキュー呼び出し結果の凡例           |テキスト                     |呼び出しキューの結果に基づいて凡例項目を設定する                             |
|呼び出しキュー ターゲットの種類                  |テキスト                     |***呼び出しリダイレクト ターゲットの型-可能な値:***<br><br>§ ApplicationEndpoint<br>§ メールボックス<br>§ その他<br>§ ユーザー |
|呼び出しキュー ターゲットの種類の凡例           |テキスト                     |呼び出しキューターゲットの種類に基づいて凡例項目を設定する                        |
|呼び出しの種類<sup>1</sup>                   |テキスト                     |呼び出し可能な値の種類:<br><br>§ 外部<br>§ 内部             |
|CQ 名                                 |テキスト                     |呼び出しキューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **次のようになります: cq_test** |
|CQ 時間                                 |整数             |通話キュー呼び出し開始時間                                                 |
|日付                                    |日付/時刻                |通話キュー呼び出しの開始日時 (時間)                                 | 
|DateTimeCQName                          |テキスト                     |fCallQueueFinalStateAction でフィルター処理するための一意のキー                     |
|PSTN 接続の種類                  |テキスト                     |呼び出し可能な値の種類:<br><br>§ ExternalCall<br>§ InternalCall     |
|PSTN 合計分数                      |整数             |要約: 合計<br>PSTN 通話の合計使用量 (分単位)                       |
|通話数の合計 (メジャー)             |整数             |呼び出し回数と同じですが、呼び出しがない場合は 0 になります                          |
|TotalCallCount (Measure)                |整数             |要約: 合計<br>通話数                                                |


#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction CQD フィールドの説明

|名前                                    |データ型                |説明                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|平均通話時間 (秒)         |10 進数           |要約: 合計<br>破棄された呼び出しの平均通話時間 (秒単位)    |
|呼び出しキューの平均期間 (秒)       |10 進数           |要約: 合計<br>応答した呼び出しの平均待機時間 (秒単位)           |
|平均通話時間の平均 (メジャー)  |整数             |平均通話時間 (秒) と同じですが、呼び出しがない場合は 0 になります   |
|平均 CQ 期間の平均 (メジャー)    |整数             |呼び出しキューの平均期間 (秒) と同じですが、呼び出しがない場合は 0 になります |
|通話数                              |整数             |要約: 合計<br>通話の数                                         |
|呼び出しキュー呼び出しの結果                  |テキスト                     |呼び出しキュー呼び出しの最終的な状態 -可能な値:<br><br>§ agent_joined_conference (応答済みの電話会議モードの呼び出し)<br>§ 拒否済み<br>§ 切断済み<br>§ エラー<br>§ 失敗しました<br>§ 無効<br>§ overflown (オーバーフロー条件が満たされました)<br>§ timed_out (タイムアウト条件が満たされている)<br>§ transferred_to_agent (応答転送モード呼び出し {default} |
|呼び出しキュー呼び出し結果の凡例           |テキスト                     |通話キュー呼び出し結果に基づいて凡例項目を設定する                      |
|キューの最終的な状態の呼び出しアクション           |テキスト                     |呼び出しキューの最終的なアクション-可能な値:<br><br>§ 切断 (timed_out呼び出し)<br>§ disconnect_with_busy (オーバーフロー呼び出し)<br>§ failed_to_accept_call<br>§ 前方<br>§ shared_voicemail<br>§ その他<br>§ ボイスメール                |
|CQ 名                                 |テキスト                     |呼び出しキューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **次のようになります: cq_test** |
|日付                                    |日付/時刻                |通話キュー呼び出しの開始日時 (時間)                                 |
|DateTimeCQName                          |テキスト                     |fCallQueueFinalStateAction でフィルター処理するための一意のキー                     |
|IsAbandoned                             |True/false               |True の呼び出しがエージェントによって応答されない場合                                   |


### <a name="cloud-call-queue-agent-timeline"></a>Cloud Call Queue Agent Timeline

#### <a name="report-description"></a>レポートの説明

|[レポート] セクション                                          |説明                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|エージェント別の呼び出し数                                |呼び出しキューとエージェントによる呼び出しの分散                |
|エージェントとすべてのキューによる配布                     |エージェントと呼び出しキューによる呼び出しの配布                |
|テーブル (右下)                                    |平均通話時間と合計通話時間を持つエージェント別の呼び出しの分布 |
|エージェント別の平均通話時間 (秒)                |エージェントによる呼び出しの平均期間 (秒)                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD テーブルとフィールド マッピングへのレポート

|[レポート] タブ            |レポート テーブル名           |ソース テーブル名         |グローバル フィルター       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|エージェントのタイムライン        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |なし                |


|[レポート] セクション                                |使用されるフィールド                         |適用されたフィルター       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|日付セレクター                                 |Datetime                              |なし                  |
|エージェント ユーザー名セレクター                       |エージェント名                            |なし                  |
|キュー リソース アカウント セレクターの呼び出し          |CQ 名                               |なし                  |
|エージェント別の呼び出し数                      |エージェント名<br>通話数<br>Hour      |なし                  |
|エージェントと呼び出しキュー別の配布          |エージェント名<br>平均通話時間 (秒)<br>通話数<br>CQ 名 |なし                      |
|左下                                   |エージェント名<br>平均通話時間 (秒)<br>通話数<br>通話時間 (分)<br>CQ 名<br>Hour<br>MM-DD | なし |
|エージェント別の平均通話時間 (秒)      |エージェント名<br>平均通話時間 (秒) | なし |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD フィールドの説明

|名前                                    |データ型                |説明                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|エージェント名                              |テキスト                     |ユーザー UPN<br>完全なユーザー名が **user@microsoft.com** の場合、この値は **次** のようになります。 |
|平均通話時間 (秒)         |10 進数           |要約: 合計<br>応答呼び出しキュー呼び出しの平均継続時間 (秒単位) |
|通話数                              |整数             |要約: 合計<br>エージェントによって応答された呼び出しの数     |
|通話時間 (分)                 |整数             |要約: 合計<br>応答された通話キュー呼び出しの呼び出しの合計時間 (分単位) (切り捨てから最も近い分)  |
|CQ 名                                 |テキスト                     |呼び出しキューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **次のようになります: cq_test** |
|日付                                    |日付                     |呼び出しの日付                                             |
|Datetime                                |Datetime                 |呼び出しの日付                                             |
|Hour                                    |整数             |時間の呼び出し                                             |
|MM-DD                                   |テキスト                     |通話の月と日                                    |


> [!NOTE]
> 呼び出しが最初の呼び出しキューに到着すると、そのキューで既に待機している呼び出しの数が **呼び出しオーバーフロー処理** の制限に達し、リダイレクト オプションが 2 番目の呼び出しキューに新しい呼び出しを送信した場合、2 番目の呼び出しキュー内のエージェントはこのレポートの最初の呼び出しキューにあるものとして表示されます。 

## <a name="known-issues"></a>既知の問題

- 呼び出しキューと自動応答は、呼び出しキューまたは自動応答名の代わりにリソース アカウントの ID で表示されます。  自動応答または通話キューのすべてのトラフィックを表示するには、自動応答または通話キューに割り当てられているすべてのリソース アカウントを選択する必要があります。

- 通話キュー/自動応答データは個人データと見なされ、データプライバシー保持ポリシーの対象であるため、ダッシュボードでは 28 日間の履歴しか使用できません。

- 一部のシナリオでは、クラウド通話キュー エージェントタイムライン レポートのエージェント応答通話数が、Teams クライアントの通話履歴に表示される通話の数と異なる場合があります。 Teams クライアントの通話履歴が正しい。 サポートは調査中ですが、現時点では修復可能な見積もり時間はありません。

- <sup>1</sup> 自動応答と **呼び出** しキューのグラフの着信呼び出し元は、最初の呼び出しレグ ソースではなく、最終的な呼び出しレグ ソースを示します。 たとえば、自動応答が外部通話を受信し、その呼び出しを別の自動応答または呼び出しキューに転送した場合、 **着信呼び出し元** は内部として報告されます。

## <a name="version-history"></a>バージョン履歴
|バージョン  |発行日     |Filename                                                           |説明                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|1.63     |2022 年 8 月 24 日    |CQD Teams 自動応答&通話キュー履歴レポート V1.63.pbit |以下を参照してください。<br>CQD Teams 自動応答&通話キュー履歴レポート - ダウンロードした zip ファイルの変更Log.docxを変更して変更の一覧を表示する                                                                             |
|1.60     |2022 年 7 月 22 日      |CQD Teams 自動応答&通話キュー履歴レポート V1.60.pbit |以下を参照してください。<br>CQD Teams 自動応答&通話キュー履歴レポート - ダウンロードした zip ファイルの変更Log.docxを変更して変更の一覧を表示する                                                                             |
|1.00     |2020 年 11 月 5 日   |CQ と AA を組み合わせた Analytics 20201105.pbit                         |初期リリース                                     |



