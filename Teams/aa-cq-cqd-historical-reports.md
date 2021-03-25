---
title: 自動応答 & キューの履歴レポート
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
description: 通話品質ダッシュボード Power BI レポートを使用して、通話品質ダッシュボードの履歴データ自動応答を表示する方法について説明します。
ms.openlocfilehash: d3c8bd7181bab9ee7c199aedbac8a6fcc4c78d75
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121545"
---
# <a name="auto-attendant--call-queue-historical-report"></a>自動応答 & キューの履歴レポート

CQD Teams 自動応答 &通話キューの履歴レポート Power BI テンプレートには、次の 3 つのレポートがあります。

- 自動応答 – 自動応答に着信する通話の分析を表示します。
- 通話キュー – 通話キューに着信する通話の分析を示します。
- エージェント タイムライン – 通話キューの呼び出しでアクティブなエージェントのタイムライン ビューを示します。

これらのレポートでは、通話品質[](CQD-Power-BI-query-templates.md)ダッシュボード データ ストアのデータを使用して、組織が自動応答や通話キューで処理される通話の数と、通話キューでのエージェントのパフォーマンスについて報告できます。

## <a name="what-are-the-requirements"></a>要件は何ですか? 

Power BI Desktop がインストールされている必要があります。 Microsoft Windows ストアから [インストールできます](https://aka.ms/pbidesktopstore)。

無料版の Power BI Desktop を使用できます。 互換性のある最小バージョンは 2.85.681.0 (2020 年 9 月) です。

## <a name="permissions-to-access-the-cqd-pipeline"></a>CQD パイプラインへのアクセス許可

CQ Analytics 履歴レポートの AA &に使用するアカウントには、CQD データ パイプラインへのアクセス許可が必要です。 詳細については [、CQD アクセスの役割](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) を参照してください。

## <a name="installation"></a>インストール 

次の手順では、Power BI Desktop をコンピューターに既にインストール済みで、CQD データ パイプラインにアクセスするために必要なアクセス許可がアカウントに与えされていることを前提とします。

次の手順を実行してください。

- [CQD Power BI クエリ テンプレートをダウンロード](https://www.microsoft.com/download/details.aspx?id=102291)し、zip ファイルをコンピューターのディレクトリに保存します。

- zip ファイルをダブルクリックして開きます。

- "CQ と AA を組み合わせた Analytics 20201105.pbit" テンプレート ファイルをダブルクリックすると、Power BI Desktop が起動します。

- CQD データ パイプライン領域を選択するように求めるメッセージが表示されます。 テナントがある地域を選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="CQD データ パイプライン領域を選択しているスクリーンショット":::

 - Skype for Business Online PowerShell コマンドレット (Get-CsTenant) を使用して地域を確認できます。ServiceInstance 出力。 
 この例の "/" の後に領域が表示されます。

   地域が noam である microsoftcommunicationsonline/noam-4a-s7。
 
 - レポートが起動し、サンプル データが表示されます。
 
 - 独自のデータを表示するには、Power  BI Desktop の [クエリ] の [ホーム] タブで [更新] をクリックしてください。

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="更新オプションを選択したスクリーンショット":::

- サインインするように求めるメッセージが表示されます。 [組織 **アカウント] を選択** し、[サインイン **] を選択します**。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="ログインを示すスクリーンショット":::

- [ **接続] を** 選び、データ更新を確認します。

## <a name="data-latency-and-aa--cq-analytics"></a>CQ 分析のデータ& AA

データは、CQD データ パイプラインで 30 分以内に利用できます。

新しい分析データを表示するには、データを更新する必要があります。 

## <a name="customization"></a>カスタマイズ 

さまざまな視覚エフェクトに表示するフィールドの追加や削除、グラフの種類の変更など、レポートの特定の視覚エフェクトの側面をカスタマイズできます。

レポートに用意されているフィールド以外のデータ フィールドを追加することはできません。

### <a name="change-color-schema"></a>色のスキーマを変更する 

次の手順は、インストール手順を既に完了しているユーザーを想定しています。

次の手順を実行してください。
- リボンの **[表示]** タブを選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="配色パターンを変更する [表示] タブを選択したスクリーンショット":::

- ドロップダウン リストからカラー スキーマを選択します。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="さまざまな配色パターンを示すスクリーンショット":::

## <a name="cqd-fields-description"></a>CQD フィールドの説明

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|自動応答 ID                 |文字列                   |AA に接続されているリソース アカウントの名前<br>例: aa_test@microsoft.com|
|自動応答チェーンの開始時刻         |datetime                 |AA チェーンの開始時刻                    |
|自動応答ディレクトリの検索方法  |文字列                   |最後のアドレス帳の検索方法        |
|自動応答転送アクション          |文字列                   |通話転送ターゲットの種類<br>使用できる値:<br>§ unknown - エンティティの種類が指定されていません<br>§ ユーザー - ユーザー エンティティ<br>§ orgaa - 組織自動応答エンティティ<br>§ hunt_group - 通話キュー エンティティ<br>§ アプリケーション - 音声アプリケーション エンティティ<br>§ external_pstn - 外部 PSTN エンティティ<br>§ shared_voicemail - 共有ボイスメール エンティティ|
|自動応答結果を表示する              |文字列                   |呼び出し結果:<br>§ unknown<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|自動応答コール フロー                |文字列                   |通話の異なる状態をカプセル化自動応答します。<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ お知らせ|
|関与自動応答か              |Boolean                  |AA が通話に関与したかどうかを示す |
|自動応答呼び出し元のアクション数      |int                      |呼び出し元による使用されるアクションの数         |
|自動応答チェーンデュレーション秒   |int                      |AA での通話の継続時間                 |
|通話キューの呼び出し結果                  |文字列                   |通話キュー呼び出しの最終状態<br>使用できる値:<br>§ エラー<br>§ 拒否<br>§ overflown<br>§ failed<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|通話キューの最終状態アクション           |文字列                   |通話キューの最終アクション<br>使用できる値:<br>§ forward<br>§ 切断<br>§ ボイスメール<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ other|
|通話キュー ID                     |文字列                   |CQ に関連付けられたリソース アカウントの名前<br>例: aa_test@microsoft.com|
|通話キューが電話会議モードである           |Boolean                  |CQ で会議モードが有効になっている場合は 1 に設定 |
|呼び出しキューターゲットの種類                  |文字列                   |想定される呼び出しリダイレクト ターゲットの種類     |
|通話キュー ID から転送される    |Boolean                  |この呼び出しが転送された CQ に接続されているリソース アカウントの名前<br>例: aa_test@microsoft.com|
|通話キュー エージェントオプトイン カウント           |int                      |通話の時点でこのキューで使用可能なエージェントの数 |
|通話キュー エージェント数                  |int                      |通話の時点でこのキューに割り当てられたエージェントの数 |
|Is Call Queue Involved                  |Boolean                  |呼び出しキューが 1 と等しいこの呼び出しに関与している場合 |


### <a name="power-bi-data-model-dimensions"></a>Power BI データ モデルのディメンション

|名前                                    |データ型                |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名                                   |文字列                   |自動応答 ID (リソース アカウント ID) |
|AACallFlow                              |文字列                   |通話の異なる状態をカプセル化自動応答します。<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ お知らせ |
|AACallResult                            |文字列                   |通話の自動応答結果:<br>§ unknown<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – AA 構成のエラー<br>§ service_terminated – 内部 AA エラー<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |文字列                   |通話の自動応答 (秒)  |
|AACount                                 |文字列                   |通話に自動応答の数         |
|AADirectorySearchMethod                 |文字列                   |呼び出しで使用される検索方法:<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name<br>
|AAStartTime                             |文字列                   |UTC での通話時間      |
|AATransferAction                        |文字列                   |通話の受け取り側:<br>§ unknown - エンティティの種類が指定されていません<br>§ ユーザー - ユーザー エンティティ<br>§ AA - 組織自動応答エンティティ<br>§ CQ - 通話キュー エンティティ<br>§ アプリケーション - 音声アプリケーション エンティティ<br>§ external_pstn - 外部 PSTN エンティティ<br>§ shared_voicemail - 共有ボイスメール エンティティ      |
|PSTNMinutes                             |int                      |分の合計使用量                          |
|通話キューの呼び出し結果                  |文字列                   |通話キュー呼び出しの最終状態<br>使用できる値:<br>§ エラー<br>§ 拒否<br>§ overflown<br>§ failed<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|通話キュー ID                     |文字列                   |CQ に関連付けられたリソース アカウントの名前     |
|呼び出しキューターゲットの種類                  |文字列                   |想定される呼び出しリダイレクト ターゲットの種類:<br>§ ユーザー<br>§ アプリケーション エンドポイント<br>§ その他     |
|通話キューの呼び出し結果                  |文字列                   |通話キュー呼び出しの最終状態<br>使用できる値:<br>§ エラー<br>§ 拒否<br>§ overflown<br>§ failed<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference           |
|通話キューの最終状態アクション           |文字列                   |通話キューの最終アクション<br>使用できる値:<br>§ forward<br>§ 切断<br>§ ボイスメール<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ other             |
|エージェント名                              |文字列                   |User UPN               |


### <a name="measures"></a>メジャー

|名前                                      |種類                       |説明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |int                        |通話中に AA のユーザーによって選択されたアクションの数  |
|PSTNMinutes                             |int                      |分の合計使用量                                  |
|TotalCallCount                          |int                      |通話数                                          |
|平均通話時間 (秒)         |int                      |通話キュー呼び出しの合計時間 (秒)     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI Graph の説明自動応答

|名前                                      |説明                            |
|:---------------------------------------|:--------------------------------------|
|着信通話ソース                    |内部/外部通話ソース別の通話<sup>の配布 1</sup>|
|ディレクトリ検索方法の合計          |検索の種類別の通話の分布                         |
|呼び出し元の操作                           |通話受信者別の通話の分布                       |
|呼び出しの結果                             |最終通話状態による通話の分布                    |
|呼び出し元のアクション数                     |通話中に使用される番号アクションによる通話の配布  |


### <a name="call-queue"></a>通話キュー

|名前                                      |説明                            |
|:---------------------------------------|:--------------------------------------|
|着信通話ソース                    |内部/外部通話ソース別の通話<sup>の配布 1</sup>   |
|通話ボリューム                             |通話キュー別の通話の配布                            |
|呼び出し元の結果                           |呼び出し結果別の通話の分布                            |
|タイムアウト/オーバーフロー呼び出し合計アクション      |呼び出し結果による NOT Forwarded(破棄) 呼び出しの分布   |
|転送/転送先の合計          |呼び出し結果によって転送された通話の配布                  |
|放棄された通話の比率                   |終了した通話数に対する成功率                    |
|平均セッションの長さ (秒)        |呼び出しの長さ (秒) を放棄/成功した通話でグループ化   |



### <a name="agent-timeline"></a>エージェントタイムライン

|名前                                                      |説明                            |
|:-------------------------------------------------------|:--------------------------------------|
|エージェントによる # 通話                                        |通話キューとエージェント別の通話の配布                 |
|エージェントと通話キュー別の通話時間 (秒) の合計   |エージェントと通話キュー別の通話の合計時間 (秒)     |
|エージェント名による平均通話時間 (秒)            |エージェント別の通話の平均継続時間 (秒)                  |



## <a name="known-issues"></a>既知の問題

- 通話キューと自動応答は、通話キュー/自動応答名の代わりにリソース アカウントの ID で表示されます。  自動応答または通話キューのすべてのトラフィックを表示するには、自動応答または通話キューに割り当てられているすべてのリソース アカウントを選択する必要があります。

- 通話キュー/自動応答データはエンド ユーザーを特定できる情報と見なされ、データ プライバシー保持ポリシーの対象となるので、ダッシュボードでは 28 日間の履歴のみを利用できます。

- <sup>1</sup> **自動応答と** 通話キュー のグラフの着信通話ソースには、最初の通話レグ ソースではなく、最終的な通話レグ ソースが表示されます。 たとえば、自動応答が外部通話を受信し、その通話を別の自動応答または通話キューに転送する場合、着信通話ソースは内部として報告されます。
