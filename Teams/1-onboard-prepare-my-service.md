---
title: クラウド 音声サービスの展開を準備する
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: オンボーディング チェックリストを使用して、Microsoft 365 または Office 365 for Teams を準備し、Teams のコア機能、ネットワーク、クラウド 音声ワークロードを構成します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 42ded974ba5f4400bdcb5796410a8277fbed4488
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103973"
---
# <a name="prepare-my-service"></a>サービスを準備する

この記事では、組織のクラウド 音声サービスを準備するための要件の概要を説明します。 適切に準備することで、組織にクラウド音声機能を提供する準備が整います。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Microsoft Teams 音声ワークロードのオンボーディング チェックリスト

次のチェックリストでは、Microsoft Teams の電話会議、通話プランを含む電話システム ("通話プラン")、電話システムダイレクト ルーティング ("ダイレクト ルーティング") 機能を実装する手順について説明します。

*  [Microsoft 365 または Office 365 for Teams を準備する](onboarding-checklist-enable-office-365.md)

*  [Teams のコア機能を構成する](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [ネットワークを準備する](prepare-network.md)

*  [Teams でクラウド音声ワークロードを構成する](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Teams で直接ルーティングを構成する](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

これらのチェックリストのタスクとアクティビティは、Teams でのクラウド音声機能のすべての展開に適用される主要な "To Do" アイテムです。 自分の Teams の旅に固有のアクティビティやタスクを含めるチェックリストをカスタマイズできます。

>[!NOTE]
>このガイダンスでは、通話プラン、電話会議、ダイレクト ルーティングのみを対象にしています。 Teams を使用する場合は、Microsoft Teams [の概要を確認します](teams-overview.md)。 Teams の展開を計画する一般的なガイダンスについては、Microsoft Teams でのチャット、チーム、チャネル、アプリの展開 [から開始します](deploy-chat-teams-channels-microsoft-teams-landing-page.md)。

提供されたチェックリストを使用して、個々のアクティビティとタスクの状態を追跡し、重要な手順をスキップしていないか確認します。 各アクティビティには、必要なアクションの詳細な説明と、そのアクティビティを完了するために使用できる追加情報への参照が含まれています。

チェックリストを順番に実行することをお勧めしますが、正確な順序は展開の範囲と環境の構成と複雑さによって異なります。 これらのチームは、"greenfield" Teams の展開 (以前の Skype for Business Online プレゼンスがない展開) または Skype for Business Online から Teams への移行のいずれかをサポートするために編成されています。 Skype for Business Online から移行する場合は、これらのアクティビティの一部を既に完了している可能性があります。この時点では無視できます。

サイトごとにユーザーのオンボーディングを行う場合は、これらのチェックリストの補足ガイドとして、音声用サイト有効化プレイブック [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) を使用することを強くお勧めします。

>[!NOTE]
>構成設定の大部分は、Teams と Skype for Business Online の間で一般的です。 これらの設定を構成するには、Microsoft 365 管理センターと Microsoft Teams 管理センターを使用します。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>オンボーディング チェックリストの完了を監督する責任は誰ですか?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次の手順</td><td><ul><li>オンボーディング チェックリストをダウンロードします。</li><li>組織の展開計画に従って、オンボーディング チェックリスト項目をステップ バイ ステップで実行します。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>オンボーディングを続行する

これらのチェックリストを完了すると、Teams の展開に音声機能が正常に追加されます。

次の手順として、音声用サイト有効化プレイブック [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) を使用して、各サイトでユーザーをオンボードし、サイト固有の重要なアクティビティを計画して実行するのに役立ちます。

-   サイト別の準備が整ったサイトの展開計画

-   サービス管理プロセスを確立する

-   テストと修復を実行する

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Teams でクラウド音声ワークロードをテストする

Teams クラウド 音声ビジネスの成功計画と技術実装計画をビジョンフェーズの一環として定義し、管理センターで必要な構成を実行したら、次の手順は、機能、機能、ユーザビリティを通じて組織の期待と要件が満たされる検証です。 実稼働環境にパイロットまたは最終的な展開を展開する前に、この検証手順を実行する必要があります。

ビジョン フェーズで定義したビジネスの成功計画を活用して、テスト フェーズ中に評価されるアクティビティ、期待値、機能/機能テスト ケース、全体的な範囲を決定するベースとして使用できます。

## <a name="define-your-testing-approach"></a>テストのアプローチを定義する

最も簡単な形式では、テストのアプローチは、電話会議、通話プラン、またはダイレクト ルーティング サービスの機能を確認し、範囲内のユーザーに対して機能要件が満たされるのを確認するためのテスト計画の開発に基づいて行います。 電話会議の実装のオンボード フェーズのテスト計画の例を次に示します。


| テストする電話会議機能 | 結果の概要 | その他のメモ |
|------------|-----------------|------------------|
| 電話会議のダイヤルイン情報を含む臨時の Teams 会議をスケジュールする | 合格/不合格   | TBD |
| PSTN からダイヤルイン情報を含む会議にダイヤルインして音声会議に電話を使う | 合格/不合格 | TBD |
| PSTN 経由でダイヤルアウトして既存の会議に他のユーザーを参加する | 合格/不合格 | TBD |



| 通話プランまたは直接ルーティング機能をテストする | 結果の概要 | その他のメモ |
|----------------------------------------------------|-----------------|------------------|
| PSTN 番号をダイヤルして PSTN 通話を発信する       | 合格/不合格       | TBD |
| PSTN 番号を外部回線 (携帯電話、固定電話) からダイヤルして PSTN 通話を受信する | 合格/不合格 | TBD|
| Teams ユーザー間で PSTN 通話を転送する | 合格/不合格 | TBD |


>[!TIP]
>テスト ケースの作成を開始点として支援するには、Teams 会議と通話で利用できるユーザー ガイダンス [の一覧を参照してください](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Teams のクラウド音声ワークロードをセットアップする

テストのアプローチを定義したら、次の手順は、Teams クラウド音声機能の範囲内でサービス環境とユーザーを構成します。

詳細については、以下を参照してください。

- [音声会議での電話会議の計画  ](./cloud-voice-landing-page.md)

- [Microsoft Teams の電話会議を設定する](set-up-audio-conferencing-in-teams.md)

- [通話プランを使用した電話システムの技術計画](calling-plan-landing-page.md)

- [Skype for Business および Microsoft Teams の通話プランをセットアップする](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [ダイレクト ルーティングを計画する](./direct-routing-plan.md)

- [ダイレクト ルーティングを構成する](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>テスト計画を実行する

[//]: # (編集は問題ありませんか?"ユーザー" は私には少しあいまいに見えました。)
ユーザー環境とサービスを構成した後、テストの最後の手順には、機能と機能の検証に焦点を当てたテスト 計画の実行が含まれます。 

**電話会議のテストの前提条件と、スコープ内のユーザーとサイトの想定:**

-   電話会議サービスのビジネス 用の使用例の定義が完了しました。

-   電話会議に必要なライセンスが利用可能で、割り当て済みです。

-   組織サイトとユーザー グループの一覧が識別されました。

-   言語設定を使用して、専用および共有の電話会議ダイヤルの番号の一覧が識別され、構成されています。

-   [組織に](what-are-communications-credits.md) 通信クレジット (必要な場合) が設定されています。

-   電話会議会議ブリッジの設定が識別され、構成されています (PIN の長さ、入退出通知、有効化通知の基本設定)。

-   電話会議のダイヤルアウト シナリオをサポートするテナント会議ポリシーとダイヤル プランの設定は、識別、構成、適用されています。

-   電話会議のコンプライアンス要件が特定され、構成されています。

**対象となるユーザーとサイトの前提条件と前提条件をテストする通話プラン:**

-   通話プラン サービスのビジネス 用の使用例の定義が完了しました。

-   通話プランに必要なライセンスが利用可能で、割り当て済みです。

-   組織サイトとユーザー グループの一覧が識別されました。

-   ユーザーに割り当てられる電話番号は、取得または Microsoft に移植され、テナント ポータルで利用できます。

-   [組織に](what-are-communications-credits.md) 通信クレジット (必要な場合) が設定されています。

-   通話プランのシナリオをサポートするテナント ユーザー ポリシーとダイヤル プランの設定は、識別、構成、適用されています。

-   通話プランのコンプライアンス要件が特定され、構成されています。

**スコープ内のユーザーとサイトのダイレクト ルーティング テストの前提条件と想定:**

-   ダイレクト ルーティング サービスのビジネス 用の使用例の定義が完了しました。

-   直接ルーティングに必要なライセンスが利用可能で、割り当て済みです。

-   組織サイトとユーザー グループの一覧が識別されました。

-   認定 [されたセッション ボーダー コントローラー (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) が電話システムと展開、構成、ペアリングされています。

-   エンタープライズ ボイスが有効になっているので、電話番号が割り当て済みです。

-   音声ルーティング ポリシーは、識別、構成、割り当て済みです。

-   Microsoft Teams は、範囲内のユーザーの優先呼び出しクライアントとして設定されています。
 
-   ダイレクト ルーティングのコンプライアンス要件が特定され、構成されています。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>展開する電話会議機能を決定する (サービス決定)。</li><li>電話会議のユーザー機能要件を特定します。</li><li>電話会議のサービス構成要件を特定します。</li><br><li>ダイレクト ルーティングと通話プランの配置と構成を決定します。<li>展開する電話システム機能を決定する (サービス決定)。</li><li>通話プランまたはダイレクト ルーティングのユーザー機能要件を特定します。</li><li>通話プランまたはダイレクト ルーティングのサービス構成要件を特定します。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次の手順</td><td><ul><li>テスト計画のアプローチを開発して文書化します。</li><li>電話会議機能の範囲でサービス環境とユーザーを準備します。</li><li>通話プランまたはダイレクト ルーティング機能の範囲でサービス環境とユーザーを準備します。</li><li>有効にする電話会議機能のテスト検証を実行します。</li><li>有効にする通話プランまたはダイレクト ルーティング機能のテスト検証を実行します。</li><li>テストの失敗がある場合は、構成が正しいか確認し、コミュニティの記事を確認し、必要に応じてサポート ケースを上げてください。</li></ul></td></tr>
</table>


Teams で電話会議のテストを実行する方法の詳細なガイダンスについては、電話会議の詳細なテスト [ガイドを参照してください](./deploy-audio-conferencing-teams-landing-page.md)。

Teams で通話プランのテストを実行する方法の詳細なガイダンスについては、電話システムの詳細なテスト [ガイドを参照してください](./cloud-voice-landing-page.md)。

<!--ENDOFSECTION-->