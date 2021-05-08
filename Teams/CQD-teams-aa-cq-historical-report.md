---
title: CQD レポートをPower BIして通話キュー履歴自動応答 &を表示する
ms.author: colongma
author: clyvr
manager: roykuntz
ms.reviewer: mikedav, siunies, gageames
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 通話品質ダッシュボード レポートを使用して、通話Power BI履歴データ自動応答を表示する方法について説明します。
ms.openlocfilehash: cfd72d0397407205aef729188c630e99148f154c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111513"
---
# <a name="what-are-the-requirements"></a>要件は何ですか? 
インストールする必要Power BI Desktopがあります。 Microsoft Windows Store[からインストールできます](https://aka.ms/pbidesktopstore)。

無料バージョンの Power BI Desktop。 互換性のある最小バージョンは 2.85.681.0 (2020 年 9 月) です。

## <a name="permissions-to-access-the-cqd-pipeline"></a>CQD パイプラインにアクセスするためのアクセス許可
CQ Analytics 履歴レポートの AA &に使用するアカウントには、CQD データ パイプラインにアクセスするためのアクセス許可が必要です。 詳細については [、CQD アクセス ロールを](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 参照してください。

## <a name="installation"></a>インストール 
次の手順では、コンピューターに Power BI Desktop を既にインストールし、アカウントに CQD データ パイプラインにアクセスするために必要なアクセス許可を持っている必要があります。

次の手順を実行してください。
- [CQD ファイルをダウンロードTeams 自動応答 &キュー履歴レポート テンプレート](./aa-cq-cqd-historical-reports.md)を呼び出し、コンピューター上のディレクトリに保存します。

- テンプレートをダブルクリックすると、Power BI Desktop表示されます。

- CQD データ パイプライン リージョンを選択するように求めるメッセージが表示されます。 テナントがあるリージョンを選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="管理センターの [通話品質] ダッシュボード ボタンTeamsスクリーンショット":::

 - このリージョンは、Skype for Business Online PS コマンドレット (Get-CsTenant) を使用して確認できます。ServiceInstance 出力。 
 リージョンは、次の例の / の後に表示されます。 
 
   リージョンが noam である microsoftcommunicationsonline/noam-4a-s7。
   
 - レポートが起動し、サンプル データが表示されます。
 
 - 独自のデータを表示するには、[ホーム] タブの [クエリ] の [更新] をクリックPower BI Desktop。

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="管理センターの [通話品質] ダッシュボード ボタンTeamsスクリーンショット":::

- その後、サインインを求めるメッセージが表示されます。 [組織 **アカウント] を選択** し、[サインイン **] を選択します**。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="管理センターの [通話品質] ダッシュボード ボタンTeamsスクリーンショット":::

- [Connect]**を** 選択し、データの更新を確認します。

## <a name="data-latency-any-aa--cq-analytics"></a>データ待機時間 CQ 分析& AA
データは、CQD データ パイプラインで 30 分以内に利用できます。

新しい分析データを表示するには、データを更新する必要があります。 

## <a name="customization"></a>カスタマイズ 
さまざまな視覚エフェクトに表示されるフィールドの追加や削除、グラフの種類の変更など、レポートの特定の視覚エフェクトの側面をカスタマイズできます。

レポートで指定したデータ フィールド以外のデータ フィールドを追加することはできません。

### <a name="change-color-schema"></a>カラー スキーマを変更する 
次の手順では、インストール手順が既に完了済みである前提で説明します。

次の手順を実行してください。
- リボンの **[表示] タブ** を選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="管理センターの [通話品質] ダッシュボード ボタンTeamsスクリーンショット":::

- ドロップダウン リストからカラー スキーマを選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="管理センターの [通話品質] ダッシュボード ボタンTeamsスクリーンショット":::


## <a name="cqd-fields-description"></a>CQD フィールドの説明

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|自動応答 ID                 |string                   |AA にアタッチされているリソース アカウントの名前<br>例: aa_test@microsoft.com|
|自動応答 チェーンの開始時刻         |datetime                 |AA チェーンの開始時刻                    |
|自動応答 ディレクトリ検索メソッド  |string                   |最後のアドレス帳の検索方法        |
|自動応答転送アクション          |string                   |通話転送ターゲットの種類<br>値の例は次のとおりです。<br>§ unknown - エンティティの種類が指定されていません<br>§ user - user entity<br>§ orgaa - 組織自動応答エンティティ<br>§ hunt_group - Queue エンティティの呼び出し<br>§ application - 音声アプリケーション エンティティ<br>§ external_pstn - 外部 PSTN エンティティ<br>§ shared_voicemail - 共有ボイスメール エンティティ|
|自動応答結果の呼び出し              |string                   |呼び出し結果:<br>§ unknown<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|自動応答通話Flow                |string                   |呼び出しの異なる状態自動応答します。<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ announcement|
|Is 自動応答 Involved              |Boolean                  |AA が呼び出しに関与したかどうかを示します |
|自動応答呼び出し元アクション数      |int                      |呼び出し元が使用したアクションの数         |
|自動応答 チェーンの継続時間 (秒)   |int                      |AA での呼び出しの期間                 |
|キュー呼び出しの結果を呼び出す                  |文字列                   |キュー呼び出しの最終状態を呼び出す<br>指定できる値:<br>§ error<br>§ declined<br>§ overflown<br>§ failed<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|呼び出しキューの最終状態アクション           |文字列                   |キューの最後のアクションを呼び出す<br>指定できる値:<br>§ forward<br>§ disconnect<br>§ ボイスメール<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ other|
|キュー ID の呼び出し                     |文字列                   |CQ にアタッチされているリソース アカウントの名前<br>例: aa_test@microsoft.com|
|通話キューが電話会議モードである           |Boolean                  |CQ で会議モードが有効になっている場合は 1 に設定 |
|呼び出しキュー ターゲットの種類                  |文字列                   |予想される呼び出しリダイレクト ターゲットの種類     |
|通話キュー ID から転送    |Boolean                  |この呼び出しが転送された CQ にアタッチされているリソース アカウントの名前<br>例: aa_test@microsoft.com|
|Call Queue Agent Opt In Count           |int                      |呼び出しの時点でこのキューで使用可能なエージェントの数 |
|Call Queue Agent Count                  |int                      |呼び出し時にこのキューに割り当てられたエージェントの数 |
|Is Call Queue Involved                  |Boolean                  |この呼び出しに対して呼び出しキューが関与している場合は、1 と等しくなります。 |


### <a name="powerbi-data-model-dimensions"></a>PowerBI データ モデルのディメンション

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名                                   |string                   |自動応答 ID (リソース アカウント ID) |
|AACallFlow                              |string                   |呼び出しの異なる状態自動応答します。<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>お知らせ |
|AACallResult                            |string                   |呼び出自動応答結果:<br>§ unknown<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – AA 構成のエラー<br>§ service_terminated – 内部 AA エラー<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |string                   |通話の自動応答時間 (秒)  |
|AACount                                 |string                   |呼び出自動応答関連するデータの数         |
|AADirectorySearchMethod                 |string                   |呼び出しで使用される検索メソッド:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |string                   |UTC での通話時間                            |
|AATransferAction                        |string                   |呼び出しの受信側:<br>§ unknown - エンティティの種類が指定されていません<br>§ user - user entity<br>§ AA - 組織自動応答エンティティ<br>§ CQ - キュー の呼び出しエンティティ<br>§ application - 音声アプリケーション エンティティ<br>§ external_pstn - 外部 PSTN エンティティ<br>§ shared_voicemail - 共有ボイスメール エンティティ      |
|PSTNMinutes                             |int                      |分の合計使用量                          |
|キュー呼び出しの結果を呼び出す                  |string                   |キュー呼び出しの最終状態を呼び出す<br>指定できる値:<br>§ error<br>§ declined<br>§ overflown<br>§ failed<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|キュー ID の呼び出し                     |string                   |CQ にアタッチされているリソース アカウントの名前     |
|呼び出しキュー ターゲットの種類                  |string                   |予想される呼び出しリダイレクト ターゲットの種類:<br>§ User<br>§ アプリケーション エンドポイント<br>§ Other     |
|キュー呼び出しの結果を呼び出す                  |string                   |キュー呼び出しの最終状態を呼び出す<br>指定できる値:<br>§ error<br>§ declined<br>§ overflown<br>§ failed<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|呼び出しキューの最終状態アクション           |string                   |キューの最後のアクションを呼び出す<br>指定できる値:<br>§ forward<br>§ disconnect<br>§ ボイスメール<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ other             |
|エージェント名                              |string                   |User UPN               |


### <a name="measures"></a>メジャー

|名前                                      |種類                       |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |呼び出し中に AA のユーザーによって選択されたアクションの数  |
|PSTNMinutes                             |int                      |分の合計使用量                                  |
|TotalCallCount                          |int                      |通話数                                          |
|平均通話時間 (秒)         |int                      |通話キュー呼び出しの合計時間 (秒)     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BIグラフの説明自動応答

|名前                                      |説明                            |
|:---------------------------------------|:--------------------------------------|
|着信通話ソース                    |内部/外部の呼び出し元による呼び出しの分散      |
|ディレクトリ検索方法の合計          |検索の種類別の呼び出しの分布                         |
|呼び出し元アクション                           |呼び出しレシーバー別の呼び出しの分布                       |
|呼び出し結果                             |最終的な呼び出し状態による呼び出しの分布                    |
|呼び出し元のアクション数                     |通話中に使用される番号別の呼び出しの分布  |


### <a name="call-queue"></a>通話キュー

|名前                                      |説明                            |
|:---------------------------------------|:--------------------------------------|
|着信通話ソース                    |内部/外部の呼び出し元による呼び出しの分散         |
|通話ボリューム                             |呼び出しキュー別の呼び出しの分散                            |
|呼び出し元の結果                           |呼び出し結果別の呼び出しの分布                            |
|Timeout/Overflow 呼び出しの合計アクション      |呼び出し結果による NOT forwarded(abandoned) 呼び出しの分布   |
|転送/転送ターゲットの合計          |呼び出し結果によって転送された呼び出しの分布                  |
|破棄された呼び出しの比率                   |破棄された呼び出し数に対する成功の比率                    |
|平均セッション長 (秒)        |呼び出しの長さ (秒) を破棄/成功した呼び出しでグループ化   |



### <a name="agent-timeline"></a>エージェントのタイムライン

|名前                                                      |説明                            |
|:-------------------------------------------------------|:--------------------------------------|
|エージェントによる # 呼び出し                                        |呼び出しキューとエージェント別の呼び出しの分散                 |
|エージェントと通話キュー別の合計通話時間 (秒)   |エージェントと呼び出しキュー別の呼び出しの合計時間 (秒)     |
|エージェント名別の平均呼び出し時間 (秒)            |エージェント別の呼び出しの平均継続時間 (秒)                  |



## <a name="known-issues"></a>既知の問題
- 現在、通話キューと自動応答では、通話キュー/自動応答名の代わりにリソース アカウント ID が表示されます。  自動応答または通話キューのすべてのトラフィックを表示するには、自動応答または通話キューに割り当てられているすべてのリソース アカウントを選択する必要があります。

- 現時点では、通話キュー/自動応答データはエンド ユーザーが特定できる情報と見なされ、データ プライバシー保持ポリシーの対象となるので、ダッシュボードで使用できる履歴は 28 日間のみです。
