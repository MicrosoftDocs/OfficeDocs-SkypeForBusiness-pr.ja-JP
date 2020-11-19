---
title: 自動応答 & 通話キュー履歴レポート
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: 通話品質ダッシュボードの Power BI レポートを使って、自動応答と通話キューの履歴データを表示する方法について説明します。
ms.openlocfilehash: c74e7fed254dda24ec404cbebfa0702498f46f21
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130408"
---
# <a name="auto-attendant--call-queue-historical-report"></a>自動応答 & 通話キュー履歴レポート

CQD Teams の自動応答 & 通話キューの履歴レポート Power BI テンプレートには、次の3つのレポートが用意されています。

- 自動応答-自動応答への通話の分析が表示されます。
- 通話キュー–通話キューに入ってくる通話の分析が表示されます。
- [エージェント] タイムライン–通話キュー通話でアクティブになっているエージェントのタイムラインビューが表示されます。

これらのレポートは、 [通話品質ダッシュボード](CQD-Power-BI-query-templates.md) のデータストアのデータを使用して、組織が通話キューのエージェントのパフォーマンスと共に、自動応答と通話キューによって処理されている通話の数を報告できるようにします。

## <a name="what-are-the-requirements"></a>要件を教えてください。 

Power BI デスクトップがインストールされている必要があります。 [Microsoft Windows ストア](https://aka.ms/pbidesktopstore)からインストールできます。

無料バージョンの Power BI Desktop を使用できます。 互換性のある最小バージョンは 2.85.681.0 (2020 年9月) です。

## <a name="permissions-to-access-the-cqd-pipeline"></a>CQD パイプラインへのアクセス許可

AA & CQ Analytics の履歴レポートを表示するために使用するアカウントには、CQD データパイプラインへのアクセス許可が必要です。 詳細については、 [CQD アクセスロール](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) を参照してください。

## <a name="installation"></a>インストール 

次の手順では、既にコンピューターに Power BI デスクトップがインストールされていて、CQD データパイプラインへのアクセスに必要なアクセス許可がアカウントにあることを前提としています。

次の手順を実行してください。

- [CQD POWER BI クエリテンプレート](https://www.microsoft.com/download/details.aspx?id=102291)をダウンロードして、zip ファイルをコンピューターのディレクトリに保存します。

- Zip ファイルをダブルクリックして開きます。

- "CQ and AA 20201105 Analytics" テンプレートファイルをダブルクリックすると、Power BI Desktop が起動します。

- CQD データパイプラインの地域を選択するように求められます。 テナントが配置されている地域を選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="CQD データパイプライン領域を選択するスクリーンショット":::

 - Skype for Business Online PowerShell コマンドレット (Get-CsTenant) を使って、地域を確認できます。ServiceInstance の出力。 
 次の例のように、地域は次のように表示されます。

   microsoftcommunicationsonline/noam-4a-地域が noam の s7 スマートを指定します。
 
 - サンプルデータを使ってレポートが起動します。
 
 - 自分のデータを表示するには、[ホーム] タブの [Power BI デスクトップのクエリ] で [ **更新** ] をクリックします。

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="[更新] オプションを選択するスクリーンショット":::

- サインインするように求められます。 [ **組織アカウント** ] を選択し、[ **サインイン**] を選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="ログインを示すスクリーンショット":::

- [ **接続** ] を選択して、データの更新を確認します。

## <a name="data-latency-and-aa--cq-analytics"></a>データ待機時間と AA & CQ analytics

データは、30分以内に CQD データパイプラインで利用可能になります。

新しい分析データを表示するには、データを更新する必要があります。 

## <a name="customization"></a>カット 

さまざまな視覚エフェクトに表示されるフィールドを追加または削除したり、グラフの種類を変更したりするなど、レポートの特定の視覚エフェクトをカスタマイズすることができます。

レポートに提供されたもの以外のデータフィールドを追加することはできません。

### <a name="change-color-schema"></a>色のスキーマを変更する 

次の手順では、既にインストール手順を完了していることを前提としています。

次の手順を実行してください。
- リボンの [ **表示] タブ** を選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="[表示] タブを選択して配色パターンを変更するスクリーンショット":::

- ドロップダウンリストから [color schema] を選びます。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="さまざまな配色パターンを示すスクリーンショット":::

## <a name="cqd-fields-description"></a>CQD フィールドの説明

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|自動応答の Id                 |型                   |AA に関連付けられているリソースアカウントの名前<br>例: aa_test@microsoft.com|
|自動応答チェーンの開始時刻         |datetime                 |AA チェーンの開始時刻                    |
|自動応答ディレクトリの検索方法  |型                   |最後のアドレス帳検索方法        |
|自動応答転送アクション          |型                   |通話転送のターゲットの種類<br>指定可能な値:<br>§不明-エンティティ型が指定されませんでした<br>§ユーザーとユーザーのエンティティ<br>§組織の自動応答のエンティティ<br>§ hunt_group 通話キューエンティティ<br>§アプリケーションの音声アプリケーションのエンティティ<br>§ external_pstn-外部 PSTN エンティティ<br>§ shared_voicemail-共有ボイスメールエンティティ|
|自動応答の呼び出し結果              |型                   |通話の結果:<br>§不明<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|自動応答のコールフロー                |型                   |自動応答のさまざまな状態をカプセル化します。<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§お知らせ|
|自動応答の関係              |Boolean                  |AA が通話に参加しているかどうかを示します。 |
|自動応答の呼び出し元のアクションカウント      |int                      |呼び出し元によって使用された操作の数         |
|自動応答チェーンの継続時間 (秒)   |int                      |AA の通話時間                 |
|通話キューの呼び出し結果                  |文字列                   |通話キュー通話の最終状態<br>指定可能な値:<br>§エラー<br>§拒否<br>§飛んでいる<br>§失敗<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|通話キューの最終的な状態のアクション           |文字列                   |通話キューの最終的な操作<br>指定可能な値:<br>§ forward<br>§切断<br>§ボイスメール<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§その他|
|通話キューの Id                     |文字列                   |CQ に関連付けられているリソースアカウントの名前<br>例: aa_test@microsoft.com|
|通話キューは会議モードです           |Boolean                  |CQ で会議モードが有効になっている場合は1に設定します。 |
|通話キューのターゲットの種類                  |文字列                   |期待される呼び出しのリダイレクトターゲットの種類     |
|通話キュー Id から転送された    |Boolean                  |この通話が転送された CQ に関連付けられているリソースアカウントの名前<br>例: aa_test@microsoft.com|
|通話キューエージェントのオプトインカウント           |int                      |通話中にこのキューで利用可能なエージェントの数 |
|通話キューエージェントカウント                  |int                      |通話中にこのキューに割り当てられているエージェントの数 |
|通話キューが含まれています                  |Boolean                  |通話キューがこの通話に関連する場合は、1 |


### <a name="power-bi-data-model-dimensions"></a>Power BI データモデルの寸法

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名                                   |型                   |自動応答 ID (リソースアカウント ID) |
|AACallFlow                              |型                   |自動応答のさまざまな状態をカプセル化します。<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§お知らせ |
|AACallResult                            |型                   |自動応答の呼び出しの結果:<br>§不明<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – AA 構成のエラー<br>§ service_terminated –内部 AA エラー<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|Aachきかん                         |型                   |自動応答の通話時間 (秒)  |
|AACount                                 |型                   |通話に含まれる自動応答の数         |
|AADirectorySearchMethod                 |型                   |通話で使用される検索方法:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name<br>
|AAStartTime                             |型                   |UTC の通話時間      |
|AATransferAction                        |型                   |通話の受信者:<br>§不明-エンティティ型が指定されませんでした<br>§ユーザーとユーザーのエンティティ<br>§ AA-組織の自動応答のエンティティ<br>§ CQ-通話キューエンティティ<br>§アプリケーションの音声アプリケーションのエンティティ<br>§ external_pstn-外部 PSTN エンティティ<br>§ shared_voicemail-共有ボイスメールエンティティ      |
|PSTNMinutes                             |int                      |合計分使用量                          |
|通話キューの呼び出し結果                  |型                   |通話キュー通話の最終状態<br>指定可能な値:<br>§エラー<br>§拒否<br>§飛んでいる<br>§失敗<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|通話キューの Id                     |型                   |CQ に関連付けられているリソースアカウントの名前     |
|通話キューのターゲットの種類                  |型                   |期待される呼び出しのリダイレクトターゲットの種類:<br>§ユーザー<br>§アプリケーションエンドポイント<br>§その他     |
|通話キューの呼び出し結果                  |型                   |通話キュー通話の最終状態<br>指定可能な値:<br>§エラー<br>§拒否<br>§飛んでいる<br>§失敗<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference           |
|通話キューの最終的な状態のアクション           |型                   |通話キューの最終的な操作<br>指定可能な値:<br>§ forward<br>§切断<br>§ボイスメール<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§その他             |
|エージェント名                              |型                   |ユーザー UPN               |


### <a name="measures"></a>メジャー

|名前                                      |種類                       |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |通話中に AA でユーザーによって選択されたアクションの数  |
|PSTNMinutes                             |int                      |合計分使用量                                  |
|TotalCallCount                          |int                      |通話の数                                          |
|平均通話時間 (秒)         |int                      |通話キュー通話の合計時間 (秒単位)     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI グラフの説明自動応答

|名前                                      |説明                            |
|:---------------------------------------|:--------------------------------------|
|着信通話ソース                    |内部/外部通話ソースによる通話の配布      |
|ディレクトリ検索方法の合計          |検索の種類による通話の配布                         |
|発信者番号操作                           |通話受信者による通話の配布                       |
|通話の結果                             |最終呼び出しの状態による通話の配布                    |
|発信者のアクション数                     |通話中に使用された番号による通話の配信アクション  |


### <a name="call-queue"></a>通話キュー

|名前                                      |説明                            |
|:---------------------------------------|:--------------------------------------|
|着信通話ソース                    |内部/外部通話ソースによる通話の配布         |
|通話ボリューム                             |通話キューによる通話の配布                            |
|発信者の結果                           |通話の結果による通話の配布                            |
|タイムアウト/オーバーフロー呼び出しの合計アクション      |呼び出し結果によって転送されていない (中断された) 通話の分布   |
|ターゲットの合計の転送/転送          |通話の転送結果                  |
|中止した通話の比率                   |破棄される通話カウントの成功率                    |
|平均セッション長 (秒)        |発信された通話の長さ (秒単位)、中断/成功した通話   |



### <a name="agent-timeline"></a>エージェントタイムライン

|名前                                                      |説明                            |
|:-------------------------------------------------------|:--------------------------------------|
|エージェントによる通話回数                                        |通話キューとエージェントによる通話の配布                 |
|エージェントと通話キューによる合計通話時間 (秒)   |エージェントと通話キューによる通話の合計所要時間 (秒)     |
|エージェント名による平均通話時間 (秒)            |エージェントによる通話の平均所要時間 (秒)                  |



## <a name="known-issues"></a>既知の問題

- 現在、通話キューと自動応答には、通話キュー/自動応答の名前ではなく、リソースアカウントの ID が表示されます。  自動応答または通話キューのトラフィックをすべて表示するには、自動応答または通話キューに割り当てられているすべてのリソースアカウントを選択する必要があります。

- 現在、通話キュー/自動応答データはエンドユーザーを特定できる情報であり、データのプライバシー保持ポリシーの適用対象となるため、ダッシュボードでは28日間の履歴しか使用できません。
