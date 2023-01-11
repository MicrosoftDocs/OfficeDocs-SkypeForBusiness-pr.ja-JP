---
title: GCC High と DoD の自動応答と通話キュー履歴レポート
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
ROBOTS: NOINDEX, NOFOLLOW
description: Teams 自動応答&通話キュー履歴レポート Power BI レポートを使用して、GCC High および DoD のお客様の自動応答と通話キューの履歴データを表示する方法について説明します。
ms.openlocfilehash: cde953bfd8e9c95c60c795f6de91488506c2addf
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763678"
---
# <a name="auto-attendant-and-call-queue-historical-reports-for-gcc-high-and-dod"></a>GCC High と DoD の自動応答と通話キュー履歴レポート

> [!IMPORTANT]
> V1.63 テンプレートのパブリック クラウド サポートは、2022 年 11 月 25 日に終了します。
>
> パブリック クラウドのお客様は、自動応答の V3.x.x [&通話キュー履歴レポート](aa-cq-cqd-historical-reports.md)を使用する必要があります

## <a name="v163-published-on-august-24-2022"></a>2022 年 8 月 24 日に公開された V1.63

**Teams 自動応答&通話キュー履歴レポート Power BI テンプレート** には、次の 3 つのレポートが用意されています。

- [自動応答](media/aa-cq-historical-report-sample-aa-v163.png)レポートには、自動応答に着信する通話の分析が表示されます。
- 通話キュー レポートには、 [通話キュー](media/aa-cq-historical-report-sample-cq-v163.png) に入ってくる通話の分析が表示されます。
- [エージェント タイムライン](media/aa-cq-historical-report-sample-at-v163.png) レポートには、通話キュー呼び出しでアクティブになっているエージェントのタイムライン ビューが表示されます。

これらのレポートでは、 [通話品質ダッシュボード (CQD)](CQD-Power-BI-query-templates.md) データ ストアのデータが使用されます。 

## <a name="v163-prerequisites"></a>V1.63 の前提条件

### <a name="power-bi-desktop"></a>Power BI Desktop
Power BI Desktopをインストールする必要があります。 [Microsoft Windows ストア](https://aka.ms/pbidesktopstore)から無料版をインストールして使用できます。

互換性のある最小バージョンは 2.85.681.0 (2020 年 9 月) です。

### <a name="permissions-to-access-the-cqd-pipeline"></a>CQD パイプラインにアクセスするためのアクセス許可

履歴レポートを表示するために使用するアカウントには、CQD データ パイプラインにアクセスするためのアクセス許可が必要です。 詳細については、「 [CQD アクセス ロール](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)」を参照してください。

## <a name="v163-installation"></a>V1.63 インストール 

次の手順では、コンピューターにPower BI Desktopが既にインストールされていることと、アカウントに CQD データ パイプラインにアクセスするために必要なアクセス許可があることを前提としています。

次の手順を実行します。

1. [コンピューターに CQD Power BI クエリ テンプレートの](https://www.microsoft.com/download/details.aspx?id=102291) zip ファイルをダウンロードして保存します。

2. zip ファイルを開きます。

3. テンプレート ファイルを `CQD Teams Auto Attendant & Call Queue Historical Report V1.63.pbit` 開きます。 Power BI Desktopが起動します。

4. CQD データ パイプラインリージョンを選択するように求められます。 テナントが配置されているリージョンを選択します。

     :::image type="content" source="media/aa-cq-historical-report-01-v163.png" alt-text="CQD データ パイプラインリージョンを選択しているスクリーンショット。":::

    パブリック クラウド テナント

5. テナントが配置されているリージョンは、 [Get-CsTenant](/powershell/module/skype/get-cstenant) コマンドレットを使用して取得できます。

    ```powershell
    (Get-CsTenant).ServiceInstance

    microsoftcommunicationsonline/noam-4a-s7
    ```

    リージョンは、上記の例のように、 の **/** 後に表示されます。このリージョンは です `noam`。

    GCC High テナントと DoD テナント

6. テンプレートを更新して、次のいずれかのコネクタを使用します。

   - GCCH: `https://data.cqd.gov.teams.microsoft.us/RunQuery`
   - 国防 総省： `https://data.cqd.dod.teams.microsoft.us/RunQuery`


7. サンプル データを使用してレポートが起動します。
 
8. 独自のデータを表示するには、Power BI Desktopの [クエリ] の [**ホーム**] タブで [**最新の情報に更新**] を選択 **します**。

   :::image type="content" source="media/aa-cq-historical-report-02-v163.png" alt-text="更新オプションを選択しているスクリーンショット。":::

9. サインインするように求められます。 [ **組織アカウント**] を選択し、[サインイン] を選択 **します**。

   :::image type="content" source="media/aa-cq-historical-report-03-v163.png" alt-text="V1.63 のログインを示すスクリーンショット。":::

10. [ **接続**] を選択すると、データが更新されます。

## <a name="data-latency-for-aa-and-cq-analytics"></a>AA および CQ 分析のデータ待機時間

通常、データは通話が完了してから 30 分以内に使用できます。ただし、データが表示されるまでに数時間かかる場合があります。

新しいデータを表示するには、データを更新する必要があります。

## <a name="customization"></a>カスタマイズ

さまざまな視覚化に表示するフィールドの追加や削除、グラフの種類の変更など、レポートの特定の視覚化の側面をカスタマイズできます。

レポートには、現在使用可能なすべてのデータ メトリックが含まれています。

### <a name="change-color-schema"></a>色スキーマを変更する

次の手順では、インストール手順が既に完了していることを前提としています。

次の手順を実行します。

1. リボンの **[表示] タブ** を選択します。

    :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="配色を変更する [ビュー] タブを選択しているスクリーンショット。":::

2. ドロップダウン リストからカラー スキーマを選択します。

    :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="さまざまな配色を示すスクリーンショット。":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>自動応答と通話キューの履歴レポートの定義

### <a name="cloud-auto-attendant-analytics-report"></a>クラウド自動応答分析レポート

#### <a name="report-description"></a>レポートの説明

|レポート セクション                          |説明                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|着信呼び出し元<sup>1</sup>        |内部/外部呼び出し元による呼び出しの分散            |
|ディレクトリ検索方法                 |検索の種類別の呼び出しの分布                              |
|呼び出し元アクション数                     |通話中に使用される番号アクション別の呼び出しの分布       |
|AA の平均秒数                   |呼び出し元が AA で費やす平均秒数                 |
|呼び出し元の平均アクション                  |呼び出し元が AA で実行する平均アクション数               |
|結果の呼び出し                            |最終呼び出し状態による呼び出しの分散                         |
|レポートの下位セクション                 |通話フローの内訳                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD テーブルとフィールド マッピングへのレポート

|[レポート] タブ            |レポート テーブル名     |ソース テーブル名            |グローバル フィルター                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|自動応答        |fAutoAttendant        |AutoAttendant                |なし                                   |

|レポート セクション                                  |使用されるフィールド                              |適用されたフィルター     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|日付セレクター                                   |AAStartTime                                |なし                |
|時間範囲セレクター                             |AAStartHour                                |なし                |
|自動応答                                  |AA 名                                    |なし                |
|着信呼び出し元<sup>1</sup>                |通話の種類<br>TotalCallCount の合計 (メジャー) |外部呼び出し: 呼び出しの種類は外部<br>内部呼び出し: 呼び出しの種類は内部 |
|ディレクトリ検索方法                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod がabs_search_dtmfまたはabs_search_name    |
|呼び出し元アクション数                             |AACallerActionCount<br>TotalCallCount      |なし                                                             |
|AA の平均秒数                           |AAChainDuration (メジャー)                  |なし                                                             |
|呼び出し元の平均アクション                          |AACallerActionCount (Measure)              |なし                                                             |
|結果の呼び出し                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |なし                                       |
|レポートの下位セクション                         |AA 名<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>通話の種類<br>MM-DD<br>TotalCallCount |なし       |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD フィールドの説明

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名                                 |テキスト                     |自動応答にアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **aa_test@microsoft.com** されている場合、この値は **aa_test** |
|AACallerActionCount                     |整数             |要約: 合計<br>通話中に自動応答で呼び出し元によって選択されたアクションの数  |
|AACallerActionCount (Measure)          |整数             |上記と同じですが、空白ではなく呼び出しがない場合は 0 になります                              |
|AACallFlow                              |テキスト                     |自動応答呼び出し可能な値のさまざまな状態をカプセル化します。<br><br>§ abs_search<br>§ お知らせ<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |テキスト                     |最終的な呼び出しの結果 - 可能な値:<br><br>§ failed_to_establish_media (呼び出しのメディア部分を確立できませんでした)<br>§ failover_to_operator (通常、システム エラーが原因でオペレーターに転送される呼び出し)<br>§ oaa_chain_too_long (AA の脚が多すぎます)<br>§ oaa_session_too_long (AA セッションが長すぎます)<br>§ service_declined (AA が呼び出しを受け入れませんでした)<br>§ service_terminated (AA 構成によって通話が切断されるか、通話がハングアップ)<br>§ terminated_automatic_selection (AA 構成によって呼び出しが切断されます)<br>§ terminated_no_operator (演算子が定義されていないエラーが原因で呼び出しが終了しました) <br>§ terminated_transfer_failed (転送に失敗した場合に終了した呼び出し - 通常は外部番号に)<br>§ transfer_in_progress (AA->AA 転送)<br>§ transferred_to_operator (呼び出しがオペレーターに転送されました -通常、ユーザー エラーが原因)<br>§ transferred_to_receptionist (transferred_to_operatorと同じ)<br>§ transferred_to_self (呼び出しは AA の先頭に返されました -通常はメニューアナウンス オプションから)<br>§ transferred_to_shared_voicemail (通話が共有ボイスメールに転送されました)<br>§ transferred_to_user (呼び出しがユーザーに転送されました - 呼び出しキューを含む)<br>§ 不明 (不明な状態が発生しました)<br>§ user_terminated (呼び出し元がハングアップ) |
|AA 呼び出しの凡例                          |テキスト                     |AACallResult に基づいて凡例項目を設定する                               |
|AAChainDuration                         |10 進数           |要約: 合計<br>自動応答での通話時間                     |
|AAChainDuration (メジャー)               |10 進数           |上記と同じですが、空白ではなく呼び出しがない場合は 0 になります              |
|AAChainIndex                            |テキスト                     |                                                                         |
|AAConnectivityType                      |テキスト                     |呼び出し可能な値の種類:<br><br>§ ExternalCall<br>§ InternalCall |
|AACount                                 |テキスト                     |通話に関係する自動応答の数                               |
|AADirectorySearchMethod                 |テキスト                     |最後のアドレス帳の検索方法 - 可能な値:<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |10 進数           |自動応答通話の開始時刻                                           |
|AAStartTime                             |日付/時刻                |自動応答呼び出しの開始時刻                                           |
|AATransferAction                        |テキスト                     |呼び出し転送ターゲットの種類- 可能な値:<br><br>§ application - 音声アプリケーション エンティティ<br>§ external_pstn<br>§ hunt_group - Queue エンティティの呼び出し<br>§ orgaa - 自動応答エンティティ<br>§ shared_voicemail<br>§ 不明<br>§ user |
|通話の種類<sup>1</sup>                   |テキスト                     |呼び出し可能な値の種類:<br><br>§ External<br>§ 内部           |
|IsAAInvolved                            |テキスト                     |Always 1                                                                 |
|MM-DD                                   |テキスト                     |自動応答通話の月日                                            |
|PSTNMinutes                             |整数             |要約: 合計<br>合計分使用量                                     |
|TotalCallCount                          |整数             |要約: 合計<br>Always 1 - すべての呼び出しの合計を提供するために使用されます            |
|TotalCallCount の合計 (メジャー)         |整数             |上記と同じですが、空白ではなく呼び出しがない場合は 0 になります              |


### <a name="cloud-call-queue-analytics-report"></a>Cloud Call Queue Analytics レポート

#### <a name="report-description"></a>レポートの説明

|レポート セクション                          |説明                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|着信呼び出し元<sup>1</sup>        |内部/外部呼び出し元による呼び出しの分散             |
|平均待機時間 (秒)             |応答された呼び出しと破棄された呼び出しの待機時間                          |
|通話量とエージェントのオプトイン数      |呼び出しキュー別の呼び出しの分散/ エージェントオプトインの最大数  |
|結果の呼び出し                            |呼び出し結果による呼び出しの分散                               |
|破棄された呼び出し                         |呼び出しキューによる破棄された呼び出しの分散                     |
|平均セッション長 (秒)        |呼び出し結果でグループ化された通話の長さ (秒単位)                      |
|呼び出しのオーバーフロー/タイムアウトの宛先      |タイムアウトまたはオーバーフローした呼び出しの分散                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD テーブルとフィールド マッピングへのレポート

|[レポート] タブ            |レポート テーブル名                                   |ソース テーブル名                               |グローバル フィルター       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|通話キュー            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |なし                |

|レポート セクション                      |テーブル -> フィールドの使用                |適用されたフィルター       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日付セレクター                       |fCallQueueAnalytics -> Date           |なし                  |
|時間範囲セレクター                 |fCallQueueAnalytics -> CQHour         |なし                  |
|キュー リソース アカウントの呼び出し         |fCallQueueAnalytics -> CQ 名        |なし                  |
|着信呼び出し元<sup>1</sup>    |fCallQueueAnalytics ->呼び出し回数の合計 (メジャー)<br>fCallQueueAnalytics -> 呼び出しの種類    |外部呼び出し: 呼び出しの種類は外部<br>内部呼び出し: 呼び出しの種類は内部 |
|平均待機時間 (秒)-回答前 |fCallQueueFinalStateAction -> 平均 CQ 期間の平均 (メジャー) |通話キュー呼び出し結果がagent_joined_conferenceまたはtransferred_to_agent|
|平均待機時間 (秒)-破棄前 |fCallQueueFinalStateAction -> 平均通話時間の平均 (メジャー) |通話キュー呼び出し結果がagent_joined_conference、transferred_to_agent、オーバーフロー、timed_out |
|通話ボリュームとエージェントのOpt-In数   |fCallQueueAnalytics -> 呼び出し数<br>fCallQueueAnalytics -> 通話キュー エージェントオプトインカウント<br>fCallQueueAnalytics -> CQ 名<br>fCallQueueAnalytics -> Date |なし |
|破棄された呼び出し                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | 呼び出しキュー呼び出し結果の凡例が破棄されました |
|平均セッション長 (秒)    |fCallQueueFinalStateAction ->平均通話キュー期間 (秒)<br>通話キュー呼び出しの結果の凡例 |平均通話キュー期間 (秒) > 0 |
|呼び出しのオーバーフロー/タイムアウトの宛先  |fCallQueueAnalytics -> 呼び出し数<br>fCallQueueAnalytics -> 呼び出しキューターゲットの種類<br>fCallQueue ターゲット型の凡例 |呼び出しキューのターゲットの種類の凡例に破棄済みとエージェント応答が含まれていない |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD フィールドの説明

|名前                                    |データ型                |説明                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|通話数                              |整数             |要約: 合計<br>通話の数                                          |
|キュー エージェントの呼び出し数                  |整数             |要約: 合計<br>呼び出しキューに構成されているエージェントの数            |
|通話キュー エージェントオプトイン数           |整数             |要約: 合計<br>呼び出しキューにオプトインされたエージェントの数              |
|通話キューの呼び出し結果                  |テキスト                     |呼び出しキュー呼び出しの最終的な状態 - 可能な値:<br><br>§ agent_joined_conference (応答された会議モードの呼び出し)<br>§ 拒否されました<br>§ 切断済み<br>§ エラー<br>§ 失敗しました<br>§ が無効です<br>§ overflown (オーバーフロー条件が満たされました)<br>§ timed_out (タイムアウト条件が満たされました)<br>§ transferred_to_agent (応答転送モード呼び出し {default}) |
|通話キュー呼び出しの結果の凡例           |テキスト                     |通話キューの結果に基づいて凡例項目を設定する                             |
|キュー ターゲットの種類を呼び出す                  |テキスト                     |***呼び出しリダイレクト ターゲットの種類- 可能な値:***<br><br>§ ApplicationEndpoint<br>§ メールボックス<br>§ その他<br>§ ユーザー |
|呼び出しキュー ターゲットの種類の凡例           |テキスト                     |通話キュー ターゲットの種類に基づいて凡例項目を設定する                        |
|通話の種類<sup>1</sup>                   |テキスト                     |呼び出し可能な値の種類:<br><br>§ External<br>§ 内部             |
|CQ 名                                 |テキスト                     |通話キューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **cq_test** |
|CQ 時間                                 |整数             |通話キュー呼び出し開始時間                                                 |
|日付                                    |日付/時刻                |通話キュー呼び出しの開始時刻 (時間)                                 | 
|DateTimeCQName                          |テキスト                     |fCallQueueFinalStateAction でフィルター処理するための一意のキー                     |
|PSTN 接続の種類                  |テキスト                     |呼び出し可能な値の種類:<br><br>§ ExternalCall<br>§ InternalCall     |
|PSTN 合計分数                      |整数             |要約: 合計<br>PSTN 通話の合計使用量 (分)                       |
|通話数の合計 (メジャー)             |整数             |呼び出し数と同じですが、呼び出しがない場合は 0 になります                          |
|TotalCallCount (Measure)                |整数             |要約: 合計<br>通話数                                                |


#### <a name="fcallqueuefinalstateaction-cqd-fields-description"></a>fCallQueueFinalStateAction CQD フィールドの説明

|名前                                    |データ型                |説明                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|平均通話時間 (秒)         |10 進数           |要約: 合計<br>破棄された呼び出しの平均通話時間 (秒単位)    |
|平均通話キュー期間 (秒)       |10 進数           |要約: 合計<br>応答された呼び出しの平均待機時間 (秒単位)           |
|平均通話時間の平均 (測定)  |整数             |平均通話時間 (秒) と同じですが、呼び出しがない場合は 0 になります   |
|平均 CQ 期間の平均 (メジャー)    |整数             |平均通話キュー期間 (秒) と同じですが、呼び出しがない場合は 0 になります |
|通話数                              |整数             |要約: 合計<br>通話の数                                         |
|通話キューの呼び出し結果                  |テキスト                     |呼び出しキュー呼び出しの最終的な状態 - 可能な値:<br><br>§ agent_joined_conference (応答された会議モードの呼び出し)<br>§ 拒否されました<br>§ 切断済み<br>§ エラー<br>§ 失敗しました<br>§ が無効です<br>§ overflown (オーバーフロー条件が満たされました)<br>§ timed_out (タイムアウト条件が満たされました)<br>§ transferred_to_agent (応答転送モード呼び出し {default} |
|通話キュー呼び出しの結果の凡例           |テキスト                     |通話キューの呼び出し結果に基づいて凡例項目を設定します                      |
|キューの最終状態アクションを呼び出す           |テキスト                     |呼び出しキューの最終的なアクション - 可能な値:<br><br>§ 切断 (timed_out呼び出し)<br>§ disconnect_with_busy (オーバーフロー呼び出し)<br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ other<br>§ ボイスメール                |
|CQ 名                                 |テキスト                     |通話キューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **cq_test** |
|日付                                    |日付/時刻                |通話キュー呼び出しの開始時刻 (時間)                                 |
|DateTimeCQName                          |テキスト                     |fCallQueueFinalStateAction でフィルター処理するための一意のキー                     |
|IsAbandoned                             |True/false               |呼び出しがエージェントによって応答されない場合は True                                   |


### <a name="cloud-call-queue-agent-timeline-report"></a>クラウド通話キュー エージェントのタイムライン レポート

#### <a name="report-description"></a>レポートの説明

|レポート セクション                                          |説明                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|エージェント別の呼び出し数                                |呼び出しキューとエージェントによる呼び出しの分散                |
|エージェントとすべてのキューによる配布                     |エージェントと呼び出しキューによる呼び出しの分散                |
|テーブル (右下)                                    |平均通話時間と合計通話時間を持つエージェント別の呼び出しの分布 |
|エージェントごとの平均通話時間 (秒)                |エージェントごとの呼び出しの平均所要時間 (秒)                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>CQD テーブルとフィールド マッピングへのレポート

|[レポート] タブ            |レポート テーブル名           |ソース テーブル名         |グローバル フィルター       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|エージェントタイムライン        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |なし                |


|レポート セクション                                |使用されるフィールド                         |適用されたフィルター       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|日付セレクター                                 |Datetime                              |なし                  |
|エージェントのユーザー名セレクター                       |エージェント名                            |なし                  |
|キュー リソース アカウント セレクターを呼び出す          |CQ 名                               |なし                  |
|エージェント別の呼び出し数                      |エージェント名<br>通話数<br>Hour      |なし                  |
|エージェントと呼び出しキュー別の配布          |エージェント名<br>平均通話時間 (秒)<br>通話数<br>CQ 名 |なし                      |
|左下                                   |エージェント名<br>平均通話時間 (秒)<br>通話数<br>通話時間 (分)<br>CQ 名<br>Hour<br>MM-DD | なし |
|エージェント別の平均通話時間 (秒)      |エージェント名<br>平均通話時間 (秒) | なし |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD フィールドの説明

|名前                                    |データ型                |説明                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|エージェント名                              |テキスト                     |ユーザー UPN<br>完全なユーザー名が **user@microsoft.com** されている場合、この値は **user** になります。 |
|平均通話時間 (秒)         |10 進数           |要約: 合計<br>応答された呼び出しキュー呼び出しの平均時間 (秒単位) |
|通話数                              |整数             |要約: 合計<br>エージェントが応答した呼び出しの数     |
|通話時間 (分)                 |整数             |要約: 合計<br>応答された通話キュー呼び出しの合計通話時間 (分単位) (切り捨てて最も近い分)  |
|CQ 名                                 |テキスト                     |通話キューにアタッチされているリソース アカウントの名前<br><br>完全なリソース アカウント名が **cq_test@microsoft.com** されている場合、この値は **cq_test** |
|日付                                    |日付                     |通話日                                             |
|Datetime                                |Datetime                 |通話日                                             |
|Hour                                    |整数             |通話時間                                             |
|MM-DD                                   |テキスト                     |通話の月と日                                    |


> [!NOTE]
> 呼び出しが最初の呼び出しキューに到着すると、そのキューで既に待機している呼び出しの数が **呼び出しオーバーフロー処理** の制限に達し、リダイレクト オプションが 2 番目の呼び出しキューに新しい呼び出しを送信した場合、2 番目の呼び出しキュー内のエージェントはこのレポートの最初の呼び出しキューに含まれていると表示されます。 

## <a name="known-issues"></a>既知の問題

- 通話キューと自動応答は、呼び出しキュー/自動応答名ではなく、リソース アカウントの ID によって表示されます。  自動応答または通話キューのすべてのトラフィックを表示するには、自動応答または通話キューに割り当てられているすべてのリソース アカウントを選択する必要があります。

- 通話キュー/自動応答データは個人データと見なされ、データプライバシー保持ポリシーの対象であるため、ダッシュボードでは 28 日間の履歴のみを使用できます。

- 一部のシナリオでは、 **クラウド通話キュー エージェント タイムライン** レポートのエージェント応答通話数が、Teams クライアントの通話履歴に表示される呼び出しの数と異なる場合があります。 Teams クライアントの通話履歴は正しいです。 サポートは調査中ですが、現時点では修復可能な推定時間はありません。

- <sup>1</sup> 自動応答およびコール キュー グラフの **着信コール ソース** には、最初のコール レッグ ソースではなく、最終的なコール レッグ ソースが表示されます。 たとえば、自動応答が外部呼び出しを受信し、別の自動応答または通話キューに通話を転送する場合、 **着信呼び出し元** は内部として報告されます。

## <a name="version-1xx-history"></a>バージョン 1.xx の履歴

変更の詳細な一覧については、「CQD Teams 自動応答&通話キューの履歴レポート - ダウンロードした zip ファイルのLog.docxを変更する」を参照してください。                         

|バージョン  |発行日     |Filename                                                           |説明                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------
|1.63     |2022 年 8 月 24 日    |CQD Teams 自動応答&通話キュー履歴レポート V1.63.pbit |                                                    |
|1.60     |2022 年 7 月 22 日      |CQD Teams 自動応答&通話キュー履歴レポート V1.60.pbit |                                                    |
|1.00     |2020 年 11 月 5 日   |CQ と AA の組み合わせ Analytics 20201105.pbit                         |初期リリース                                     |

