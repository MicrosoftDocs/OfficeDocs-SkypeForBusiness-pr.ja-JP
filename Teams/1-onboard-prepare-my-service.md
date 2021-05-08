---
title: クラウド 音声サービスをデプロイする準備をする
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: オンボード チェックリストを使用して、Teams の Microsoft 365 または Office 365 を準備し、Teams コア機能、ネットワーク、クラウド音声ワークロードを構成します。
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

この記事では、組織のクラウド 音声サービスを準備するための要件の概要を説明します。 適切に準備することで、組織にクラウド音声機能を提供する準備ができていることを確認できます。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>音声ワークロードのMicrosoft Teamsチェックリスト

次のチェックリストでは、電話会議、電話システム と通話プラン ("通話プラン")、電話システム ダイレクト ルーティング ("ダイレクト ルーティング") 機能を Microsoft Teams で実装する手順について説明します。

*  [準備Microsoft 365またはOffice 365準備Teams](onboarding-checklist-enable-office-365.md)

*  [コア機能Teams構成する](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [ネットワークを準備する](prepare-network.md)

*  [クラウド音声ワークロードを構成する Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [[ダイレクト ルーティングの構成] Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

これらのチェックリストのタスクとアクティビティは、クラウド音声機能の各デプロイに適用される主要な "To Do" Teams。 チェックリストをカスタマイズして、独自のアクティビティ体験に固有のアクティビティやタスクTeamsできます。

>[!NOTE]
>このガイダンスでは、通話プラン、電話会議、ダイレクト ルーティングのみを中心に説明します。 新しいアプリケーションを使用する場合Teamsの概要[に関するページMicrosoft Teams。](teams-overview.md) デプロイの計画に関する一般的Teams、「チャット、[チーム](deploy-chat-teams-channels-microsoft-teams-landing-page.md)、チャネル、アプリをデプロイする」から始Microsoft Teams。

提供されているチェックリストを使用して、個々のアクティビティとタスクの状態を追跡し、重要な手順をスキップしていないか確認します。 各アクティビティには、必要なアクションの詳細な説明と、そのアクティビティを完了するために使用できる追加情報への参照が含まれています。

チェックリストを順番に実行することをお勧めしますが、正確な順序は、デプロイの範囲と環境の構成と複雑さによって異なります。 "greenfield" Teams デプロイ (以前の Skype for Business Online プレゼンスがないデプロイ) または Skype for Business Online から Teams への移行をサポートするために編成されています。 Skype for Business Online から移行する場合は、これらのアクティビティの一部が既に完了している可能性があります。現在は無視できます。

サイトごとにユーザーをオンボードする場合は、これらのチェックリストの補足ガイドとして、Site [Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) を使用することを強くお勧めします。

>[!NOTE]
>構成設定の多くが、Teams Online Skype for Businessです。 これらの設定を構成Microsoft 365管理センター Microsoft Teams管理センターを使用します。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>Whoチェックリストの完了を監視する責任は何ですか?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次の手順</td><td><ul><li>オンボード チェックリストをダウンロードします。</li><li>組織の展開計画に従って、オンボーディング チェックリスト項目をステップ バイ ステップで実行します。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>オンボードを続行する

これらのチェックリストを完了すると、デプロイに音声機能が正常にTeamsされます。

次の手順として、音声用のサイト有効化プレイブック [(プレイブック)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) を使用して、各サイトでユーザーをオンボードし、サイト固有の重要なアクティビティを計画して実行するのに役立ちます。

-   準備完了サイト(サイト別) ロールアウト 計画

-   サービス管理プロセスを確立する

-   テストと修復の実行

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>クラウド音声ワークロードをテスト Teamsする

Teams クラウド音声ビジネスの成功と技術実装計画を定義して文書化し、管理センターで必要な構成を実行したら、次の手順は、機能、機能、およびユーザビリティによって組織の期待と要件が満たされるのを検証します。 この検証手順は、実稼働環境でパイロットまたは最終的なデプロイをデプロイする前に実行する必要があります。

計画フェーズで定義したビジネス成功計画を活用して、テスト フェーズ中に評価されるアクティビティ、期待値、機能/機能テスト ケース、および全体的な範囲を決定するための基礎として機能することができます。

## <a name="define-your-testing-approach"></a>テストアプローチを定義する

最も単純な形式では、テストアプローチは、電話会議、通話プラン、または直接ルーティング サービスの機能を確認し、スコープ内のユーザーに対して機能要件が満たされるのを確認するためのテスト計画の開発に基づいて行います。 電話会議実装のオンボード フェーズのテスト計画の例を次に示します。


| テストする電話会議機能 | 結果の概要 | その他のメモ |
|------------|-----------------|------------------|
| 電話会議のダイヤルTeamsを含む臨時の会議をスケジュールする | Pass/Fail   | TBD |
| PSTN からダイヤルイン情報が表示された会議にダイヤルインして音声会議に電話を使用する | Pass/Fail | TBD |
| PSTN 経由でダイヤルアウトして、他のユーザーを既存の会議に参加する | Pass/Fail | TBD |



| テストする通話プランまたはダイレクト ルーティング機能 | 結果の概要 | その他のメモ |
|----------------------------------------------------|-----------------|------------------|
| PSTN 番号をダイヤルして PSTN 通話を発信する       | Pass/Fail       | TBD |
| PSTN 番号を外部回線 (携帯電話、固定電話) からダイヤルして PSTN 通話を受信する | Pass/Fail | TBD|
| PSTN 通話を別のユーザーにTeamsする | Pass/Fail | TBD |


>[!TIP]
>テスト ケースの作成を開始点として支援するには、「会議と通話」で利用できるユーザー [Teamsを参照してください](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>クラウド音声ワークロードを設定する Teams

テストアプローチを定義したら、次の手順では、クラウド音声機能を使用するためのスコープ内のサービス環境Teams構成します。

詳細については、以下を参照してください。

- [音声会議での電話会議の計画  ](./cloud-voice-landing-page.md)

- [Microsoft Teams の電話会議を設定する](set-up-audio-conferencing-in-teams.md)

- [通話プランを使用電話システムの技術計画](calling-plan-landing-page.md)

- [通話プランをセットアップしてSkype for BusinessとMicrosoft Teams](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [ダイレクト ルーティングを計画する](./direct-routing-plan.md)

- [ダイレクト ルーティングを構成する](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>テスト計画を実行する

[//]: # (編集は問題ありませんか?"ユーザー" は私には少しあいまいに思えました。)
ユーザー環境とサービスが構成された後、テストの最後の手順には、機能と機能の検証に焦点を当てたテスト 計画の実行が含まれます。 

**電話会議テストの前提条件と、スコープ内のユーザーとサイトの前提条件:**

-   電話会議サービスのビジネス の使用事例の定義が完了しました。

-   電話会議に必要なライセンスが利用可能であり、割り当て済みです。

-   組織サイトとユーザー グループの一覧が特定されました。

-   言語を優先する番号の専用および共有電話会議ダイヤルの一覧が識別され、構成されています。

-   [通信クレジット](what-are-communications-credits.md) (必要な場合) は、組織に対して設定されています。

-   電話会議会議ブリッジの設定が識別され、構成されています (PIN の長さ、開始/終了通知、有効化通知の設定)。

-   電話会議のダイヤルアウト シナリオをサポートするテナント会議ポリシーとダイヤル プランの設定は、識別、構成、適用されています。

-   電話会議のコンプライアンス要件が特定され、構成されています。

**スコープ内のユーザーとサイトの前提条件と前提条件をテストする通話プラン:**

-   通話プラン サービスのビジネス の使用事例の定義が完了しました。

-   通話プランに必要なライセンスが利用可能で、割り当て済みです。

-   組織サイトとユーザー グループの一覧が特定されました。

-   電話ユーザーに割り当てる番号が取得または Microsoft に移植され、テナント ポータルで使用できます。

-   [通信クレジット](what-are-communications-credits.md) (必要な場合) は、組織に対して設定されています。

-   通話プランのシナリオをサポートするテナント ユーザー ポリシーとダイヤル プランの設定が識別され、構成され、適用されています。

-   通話プランのコンプライアンス要件が特定され、構成されています。

**ダイレクト ルーティング テストの前提条件と、スコープ内のユーザーとサイトの前提条件:**

-   ダイレクト ルーティング サービスのビジネス の使用事例の定義が完了しました。

-   直接ルーティングに必要なライセンスが利用可能であり、割り当て済みです。

-   組織サイトとユーザー グループの一覧が特定されました。

-   認定[セッション ボーダー コントローラー (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs)がデプロイされ、構成され、電話システム。

-   Enterpriseが有効になっている場合、電話番号が割り当て済みです。

-   音声ルーティング ポリシーが識別され、構成され、割り当て済みです。

-   Microsoft Teams、スコープ内のユーザーの優先呼び出し元クライアントとして設定されています。
 
-   直接ルーティングのコンプライアンス要件が特定され、構成されています。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>展開する電話会議機能を決定します (サービスの決定)。</li><li>電話会議のユーザー機能の要件を特定します。</li><li>電話会議のサービス構成要件を特定します。</li><br><li>直接ルーティングまたは通話プランをデプロイして構成するかどうかを決定します。<li>デプロイする電話システム機能を決定します (サービスの決定)。</li><li>通話プランまたは直接ルーティングのユーザー機能要件を特定します。</li><li>通話プランまたは直接ルーティングのサービス構成要件を特定します。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次の手順</td><td><ul><li>テスト計画のアプローチを開発して文書化します。</li><li>電話会議機能のスコープ内でサービス環境とユーザーを準備します。</li><li>通話プランまたは直接ルーティング機能のスコープでサービス環境とユーザーを準備します。</li><li>有効にする電話会議機能のテスト検証を実行します。</li><li>有効にする通話プランまたは直接ルーティング機能のテスト検証を実行します。</li><li>テストエラーが発生した場合は、構成が正しいか確認し、コミュニティ記事を確認し、必要に応じてサポート ケースを作成します。</li></ul></td></tr>
</table>


Teams で電話会議のテストを実行する方法の詳細なガイダンスについては、電話会議の詳細なテスト ガイド[を参照してください](./deploy-audio-conferencing-teams-landing-page.md)。

Teams で通話プランのテストを実行する方法の詳細なガイダンスについては、電話システム の詳細なテスト[ガイドを参照してください](./cloud-voice-landing-page.md)。

<!--ENDOFSECTION-->