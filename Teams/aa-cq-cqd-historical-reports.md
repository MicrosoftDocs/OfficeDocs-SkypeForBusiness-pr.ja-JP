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
ms.openlocfilehash: b9bb3cf0990058cd16ed35d52d07f63be6cd90fb
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024010"
---
# <a name="auto-attendant--call-queue-historical-report"></a>自動応答&通話キュー履歴レポート

Teams 自動応答&通話キュー履歴レポート Power BI テンプレートには、次の 3 つのレポートがあります。

- [自動応答 – 自動応答](media/cqd-teams-aa-cq-historical-report-sample-aa.png) に着信する呼び出しの分析を示します。
- [通話キュー – 通話キュー](media/cqd-teams-aa-cq-historical-report-sample-cq.png) に着信する通話の分析を示します。
- [エージェント タイムライン](media/cqd-teams-aa-cq-historical-report-sample-at.png) – 通話キューの呼び出しでアクティブになっているエージェントのタイムライン ビューを示します。

これらのレポートでは、 [通話品質ダッシュボード](CQD-Power-BI-query-templates.md) データ ストアのデータが使用されます。 このレポートを使用すると、組織は自動応答と通話キューによって処理される通話の数を報告できます。  また、レポートは、呼び出しキュー内のエージェントのパフォーマンスに関する分析情報も提供します。

### <a name="v160-published-on-july-22-2022"></a>2022 年 7 月 22 日に公開された V1.60

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
|着信元<sup>1</sup>        |内部/外部の呼び出し元による呼び出しの配布             |
|ディレクトリ検索メソッドの合計          |検索の種類別の呼び出しの分布                               |
|呼び出し元のアクション                           |呼び出し元別の通話の分布                             |
|結果の呼び出し                             |最終呼び出し状態による呼び出しの分布                          |
|呼び出し元のアクション数                     |通話中に使用される番号アクションによる通話の分散        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD テーブルとフィールド マッピングへのレポート

|[レポート] タブ            |レポート テーブル名     |グローバル フィルター                          |
|:---------------------|:---------------------|:--------------------------------------|
|自動応答        |fAutoAttendant        |AAStartTime は過去 28 日以内です |


|レポート テーブル名            |ソース テーブル名            |処理       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Source = AutoAttendant, <br>#"Filtered Rows" = Table.SelectRows(Source, each true), <br>#"Auto Attendant" = Table.AddColumn(#"Filtered Rows", "AA Name", each List.First(Text.Split([AAIdentity], "@"))), <br>#"Changed Type" = Table.TransformColumnTypes(#"Auto Attendant",{{"AAStartTime", type datetime}}), <br>#"Remove Columns" = Table.RemoveColumns(#"Changed Type",{"AAIdentity"}) |


|[レポート] セクション                                  |使用されるフィールド                              |適用されたフィルター     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|日付セレクター                                   |AAStartTime                                |なし                |
|自動応答                                  |AA 名                                    |なし                |
|着信元<sup>1</sup>                |通話の種類<br>TotalCallCount                |外部呼び出し: 呼び出しの種類は外部です<br>内部呼び出し: 呼び出しの種類は内部です |
|ディレクトリ検索メソッドの合計                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod がabs_search_dtmfまたはabs_search_name    |
|呼び出し元のアクション                                  |AATransferAction<br>TotalCallCount         |なし                                                             |
|AA の平均秒数<br>呼び出し元の平均アクション |AAChainDuration<br>AACallerActionCount     |なし                                                             |
|結果の呼び出し                                    |AACallResult<br>TotalCallCount             |なし                                                             |
|呼び出し元のアクション数                            |AACallerActionCount<br>TotalCallCount      |なし                                                             |
|レポートの下部セクション                         |AA 名<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>通話の種類<br>TotalCallCount |なし                |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD フィールドの説明

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名                                 |テキスト                     |自動応答にアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **aa_test@microsoft.com** されている場合、この値は **次のようになります:aa_test** |
|AACallerActionCount                     |整数             |要約: 合計<br>通話中に自動応答で呼び出し元によって選択されたアクションの数  |
|AACallFlow                              |テキスト                     |自動応答呼び出し可能な値のさまざまな状態をカプセル化します。<br><br>§ abs_search<br>§ お知らせ<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |テキスト                     |最終的な呼び出しの結果-可能な値:<br><br>§ failed_to_establish_media (通話のメディア部分を確立できませんでした)<br>§ failover_to_operator (通常はシステム エラーが原因でオペレーターに転送される呼び出し)<br>§ oaa_chain_too_long (AA で足が多すぎます)<br>§ oaa_session_too_long (AA セッションが長すぎます)<br>§ service_declined (AA が呼び出しを受け入れませんでした)<br>§ service_terminated (AA 構成が呼び出しを切断する)<br>§ terminated_automatic_selection (AA 構成は呼び出しを切断します)<br>§ terminated_no_operator (エラーが原因で呼び出しが終了し、演算子が定義されていません) <br>§ terminated_transfer_failed (転送に失敗して終了した呼び出し - 通常は expernal number)<br>***§ transferred_to_operator*** (呼び出しはオペレーターに転送されました 。通常はユーザー入力エラーが原因)<br>§ transferred_to_receptionist (transferred_to_operatorと同じ)<br>§ transferred_to_self (呼び出しは AA の先頭に返されました 。通常はメニューのお知らせオプションから)<br>§ transferred_to_shared_voicemail (通話が共有ボイスメールに転送されました)<br>§ transferred_to_user (通話がユーザーに転送された - 通話キューを含む)<br>§ unknown (不明なエラーが発生しました)<br>§ user_terminated (発信者がハングアップ) |
|AAChainDuration                         |10 進数           |要約: 合計<br>自動応答での呼び出しの継続時間                     |
|AAChainIndex                            |テキスト                     |                                                                         |
|AAConnectivityType                      |テキスト                     |呼び出し可能な値の種類:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |テキスト                     |通話に関連する自動応答の数                               |
|AADirectorySearchMethod                 |テキスト                     |最後のアドレス帳検索方法 - 可能な値:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |日付/時刻                |自動応答呼び出しの開始時刻                                           |
|AATransferAction                        |テキスト                     |転送先の種類の呼び出し可能な値:<br><br>***§ アプリケーション - 音声アプリケーション エンティティ**_<br>§ external_pstn<br>_*_§ hunt_group - キュー エンティティ_*_<br>_*の呼び出し _§ orgaa - 組織の自動応答エンティティ_**<br>§ shared_voicemail<br>§ 不明<br>§ ユーザー |
|呼び出しの種類<sup>1</sup>                   |テキスト                     |呼び出し可能な値の種類:<br><br>§ 外部<br>§ 内部         |
|IsAAInvolved                            |テキスト                     |常に 1                                                                 |
|PSTNMinutes                             |整数             |要約: 合計<br>合計分の使用量                                     |
|TotalCallCount                          |整数             |要約: 合計<br>常に 1 - すべての呼び出しの合計を提供するために使用されます            |


### <a name="cloud-call-queue-analytics"></a>Cloud Call Queue Analytics

#### <a name="report-description"></a>レポートの説明

|[レポート] セクション                          |説明                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|着信元<sup>1</sup>        |内部/外部の呼び出し元による呼び出しの分布              |
|通話ボリューム                             |呼び出しキュー別の呼び出しの分布                                |
|呼び出し元の結果                           |呼び出し結果による呼び出しの分布                                |
|タイムアウト/オーバーフロー呼び出しの合計アクション      |呼び出し結果による NOT Forwarded(Abandoned) 呼び出しの分布       |
|転送/転送ターゲットの合計          |呼び出し結果によって転送された呼び出しの分布                      |
|破棄された呼び出しの比率                   |成功した呼び出しと破棄された呼び出し数の比率                        |
|平均セッション長 (秒)        |破棄された呼び出しと成功した呼び出しによってグループ化された呼び出しの長さ (秒単位)       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD テーブルとフィールド マッピングへのレポート

|[レポート] タブ         |レポート テーブル名                                                          |グローバル フィルター |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|キューの呼び出し         |日付<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |なし          |
 
|レポート テーブル名            |ソース テーブル名            |処理       |
|:----------------------------|:----------------------------|:----------------|
|日付                        |日付                        |なし             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics, <br>#"Remove Columns" = Table.RemoveColumns(Source,{"Call Count", "Call Queue Call Result", "Date", "PSTN Connectivity Type", "Call Queue Target Type", "PSTN Total Minutes"}),<br>Distinct = Table.Distinct(#"Removed Columns") |
|fCallQueueAnalytics          |CallQueueAnalytics           |なし             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |なし             |

|[レポート] セクション                      |使用されるテーブル -> フィールド                |適用されたフィルター       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日付セレクター                       |Date -> DateTime                     |なし                  |
|キュー ID の呼び出し                 |dCQ-CQIdentity -> コール キュー ID |なし                  |
|着信元<sup>1</sup>    |fCallQueueAnalytics ->呼び出し数<br>fCallQueueAnalytics ->呼び出しの種類    |外部呼び出し: 呼び出しの種類は外部です<br>内部呼び出し: 呼び出しの種類は内部です |
|平均待機時間                    |fCallQueueFinalStateAction ->平均通話時間 (秒) |転送前: 呼び出しキュー呼び出しの結果がagent_joined_conferenceまたはtransferred_to_agent<br>ハングアップする前: 呼び出しキュー呼び出しの結果がagent_joined_conferenceまたはtransferred_to_agent |
|結果の呼び出し                         |fCallQueueAnalytics ->呼び出し数<br>fCallQueueAnalytics -> 呼び出しキュー呼び出し結果 | なし |
|タイムアウト/オーバーフロー呼び出しの合計アクション |fCallQueueFinalStateAction ->呼び出し数<br>fCallQueueFinalStateAction -> コール キューの最終状態アクション |キューの最終状態の呼び出しアクションが転送されない |
|Transfer/Forard ターゲットの合計       |fCallQueueAnalytics ->呼び出し数<br>fCallQueueAnalytics -> 呼び出しキュー ターゲットの種類 |なし |
|呼び出しボリューム                        |fCallQueueAnalytics ->呼び出し数<br>fCallQueueAnalytics -> Call Queue Identify<br>fCallQueueAnalytics -> Date |なし |
|破棄された呼び出し                     |fCallQueueAnalytics -> %Abandoned calls<br>fCallQueueAnalytics ->呼び出し数<br>fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned is True |
|平均セッション長 (秒)    |fCallQueueFinalStateAction ->平均通話時間<br>fCallQueueFinalStateAction ->日付<br>fCallQueueFinalStateAction -> IsAbandoned |なし |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>dCQ-CQIdenity CQD フィールドの説明

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|キュー ID の呼び出し                     |テキスト                     |呼び出しキューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **次のようになります: cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD フィールドの説明

|名前                                    |データ型                |説明                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|通話数                              |整数             |要約: 合計<br>通話の数                                          |
|呼び出しキュー呼び出しの結果                  |テキスト                     |呼び出しキュー呼び出しの最終的な状態 -可能な値:<br><br>§ agent_joined_conference (応答済みの電話会議モードの呼び出し)<br>§ 拒否済み<br>§ 切断済み<br>§ エラー<br>§ 失敗しました<br>§ 無効<br>§ overflown (オーバーフロー条件が満たされました)<br>§ timed_out (タイムアウト条件が満たされている)<br>§ transferred_to_agent (応答された転送モード呼び出し {default}) |
|キュー ID の呼び出し                     |テキスト                     |呼び出しキューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **次のようになります: cq_test** |
|呼び出しキュー ターゲットの種類                  |テキスト                     |***呼び出しリダイレクト ターゲットの型-可能な値:***<br><br>§ ApplicationEndpoint<br>§ メールボックス<br>§ その他<br>§ ユーザー |
|呼び出しの種類<sup>1</sup>                   |テキスト                     |呼び出し可能な値の種類:<br><br>§ 外部<br>§ 内部           |
|日付                                    |日付/時刻                |通話キュー呼び出しの開始日時 (時間) (UTC)                           | 
|IsAbandoned                             |True/false               |True の呼び出しがエージェントによって応答されない場合                                   |
|PSTN 接続の種類                  |テキスト                     |呼び出し可能な値の種類:<br><br>§ ExternalCall<br>§ InternalCall   |
|PSTN 合計分数                      |整数             |要約: 合計<br>PSTN 通話の合計使用量 (分単位)                       |

#### <a name="fcallqueueanalytics-measures-description"></a>fCallQueueAnalytics メジャーの説明

|名前                                    |データ型                |説明                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***放棄された呼び出しの割合***                 |パーセンテージ               |メジャー: 破棄された呼び出しの数/通話の合計数    |
|呼び出しの合計数                             |整数             |メジャー: エージェントが応答した呼び出しの合計        |
|TotalCallCount                          |整数             |メジャー: Sum(呼び出し数)                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction CQD フィールドの説明

|名前                                    |データ型                |説明                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|平均通話時間 (秒)         |10 進数           |要約: 合計<br>平均通話時間 (秒単位) |
|通話数                              |整数             |要約: 合計<br>通話の数                  |
|呼び出しキュー呼び出しの結果                  |テキスト                     |呼び出しキュー呼び出しの最終的な状態 -可能な値:<br><br>§ agent_joined_conference (応答済みの電話会議モードの呼び出し)<br>§ 拒否済み<br>§ 切断済み<br>§ エラー<br>§ 失敗しました<br>§ 無効<br>§ overflown (オーバーフロー条件が満たされました)<br>§ timed_out (タイムアウト条件が満たされている)<br>§ transferred_to_agent (応答転送モード呼び出し {default} |
|キューの最終的な状態の呼び出しアクション           |テキスト                     |呼び出しキューの最終的なアクション-可能な値:<br><br>§ 切断 (timed_out呼び出し)<br>§ disconnect_with_busy (オーバーフロー呼び出し)<br>§ failed_to_accept_call<br>§ 前方<br>§ shared_voicemail<br>§ その他<br>§ ボイスメール |
|キュー ID の呼び出し                     |テキスト                     |呼び出しキューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **次のようになります: cq_test** |
|日付                                    |日付/時刻                |通話キュー呼び出しの開始日時 (時間) (UTC)   |
|IsAbandoned                             |True/false               |True の呼び出しがエージェントによって応答されない場合           |


### <a name="cloud-call-queue-agent-timeline"></a>Cloud Call Queue Agent Timeline

#### <a name="report-description"></a>レポートの説明

|[レポート] セクション                                          |説明                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|# エージェントによる呼び出し                                        |呼び出しキューとエージェントによる呼び出しの分散                 |
|エージェントと通話キュー別の通話時間 (秒) の合計   |エージェントと呼び出しキューによる呼び出しの合計期間 (秒)     |
|エージェント名別の平均通話時間 (秒)           |エージェントによる呼び出しの平均期間 (秒)                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD テーブルとフィールド マッピングへのレポート

|[レポート] タブ         |レポート テーブル名        |グローバル フィルター |
|:------------------|:-------------------------|:-------------|
|エージェントのタイムライン     |fAgentTimelineAnalytics   |なし          |
 
|レポート テーブル名            |ソース テーブル名            |処理       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics, <br>#"Changed Type" = Table.TransformColumnTypes(Source,{{"Call Count", Int64.Type}, {"Call Duration (Minute)", Int64.Type}, {"Average Call Duration (Second)", type number}, {"Date", type date})|

|[レポート] セクション                                |使用されるフィールド                         |適用されたフィルター       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|エージェント名                                    |エージェント名                            |なし                  |
|呼び出しキュー名                               |呼び出しキュー名                       |なし                  |
|エージェント別の#Calls                               |エージェント名<br>通話数<br>日付      |なし                  |
|エージェントと呼び出しキュー別の配布          |エージェント名<br>通話数<br>通話時間 (分)<br>呼び出しキュー名 |なし                      |
|左下                                   |エージェント名<br>平均通話時間 (2 番目)<br>通話数<br>通話時間 (分)<br>呼び出しキュー名 | なし |
|エージェント名別の平均通話時間 (秒) |エージェント名<br>平均通話時間 (2 番目)<br>通話数<br>通話時間 (分)<br>呼び出しキュー名 | なし |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD フィールドの説明

|名前                                    |データ型                |説明                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|エージェント名                              |テキスト                     |ユーザー UPN<br>完全なユーザー名が **user@microsoft.com** の場合、この値は **次** のようになります。 |
|平均通話時間 (2 番目)          |10 進数           |要約: 合計<br>応答呼び出しキュー呼び出しの平均継続時間 (秒単位) |
|通話数                              |整数             |要約: 合計<br>エージェントに提示された呼び出しの数     |
|通話時間 (分)                  |整数             |要約: 合計<br>応答された通話キュー呼び出しの呼び出しの合計時間 (分単位) (切り捨てから最も近い分)  |
|呼び出しキュー名                         |テキスト                     |呼び出しキューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **次のようになります: cq_test** |
|日付                                    |日付                     |                                                    |


> [!NOTE]
> 1) このレポートはエージェントの観点から通話数を示しているため、このレポートの通話数の合計は、通常、 **Cloud Call Queue Analytics** レポートの通話の合計数よりも多くなります。 キュー内の各呼び出しは、応答する前に少なくとも 1 回は 1 つ以上のエージェントに提示できます。 エージェントに提示されたすべての通話キュー呼び出しは、エージェントによって応答されなかった場合でも、このレポートにカウントされます。 これら 2 つのレポート間の呼び出しカウントの違いは、すべての呼び出しのすべてのエージェントを呼び出す **アテンダント ルーティング** オプションにより顕著です。 
> 2) 呼び出しが最初に最初の呼び出しキューに到着したとき、そのキューで既に待機している呼び出しの数が **呼び出しオーバーフロー処理** の制限を超えた場合、リダイレクト オプションが 2 番目の呼び出しキューに呼び出しを送信した場合、2 番目の呼び出しキューのエージェントはこのレポートの最初の呼び出しキューに存在するものとして表示されます。 

## <a name="known-issues"></a>既知の問題

- 呼び出しキューと自動応答は、呼び出しキューまたは自動応答名の代わりにリソース アカウントの ID で表示されます。  自動応答または通話キューのすべてのトラフィックを表示するには、自動応答または通話キューに割り当てられているすべてのリソース アカウントを選択する必要があります。

- 通話キュー/自動応答データは個人データと見なされ、データプライバシー保持ポリシーの対象であるため、ダッシュボードでは 28 日間の履歴しか使用できません。

- 一部のシナリオでは、クラウド通話キュー エージェントタイムライン レポートのエージェント応答通話数が、Teams クライアントの通話履歴に表示される通話の数と異なる場合があります。 Teams クライアントの通話履歴が正しい。 サポートは調査中ですが、現時点では修復可能な見積もり時間はありません。

- <sup>1</sup> 自動応答と **呼び出** しキューのグラフの着信呼び出し元は、最初の呼び出しレグ ソースではなく、最終的な呼び出しレグ ソースを示します。 たとえば、自動応答が外部通話を受信し、その呼び出しを別の自動応答または呼び出しキューに転送した場合、 **着信呼び出し元** は内部として報告されます。

## <a name="version-history"></a>バージョン履歴
|バージョン  |発行日     |Filename                                                           |説明                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------|
|1.60     |2022 年 7 月 22 日      |CQD Teams 自動応答&通話キュー履歴レポート V1.60.pbit |以下を参照してください。<br>CQD Teams 自動応答&通話キュー履歴レポート - ダウンロードした zip ファイルの変更Log.docxを変更して変更の一覧を表示する                                                                             |
|1.00     |2020 年 11 月 5 日   |CQ と AA を組み合わせた Analytics 20201105.pbit                         |初期リリース                                     |



