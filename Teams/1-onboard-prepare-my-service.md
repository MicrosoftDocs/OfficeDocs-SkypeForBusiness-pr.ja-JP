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
description: オンボード チェックリストを使用して、TeamsのMicrosoft 365またはOffice 365を準備し、Teamsコア機能、ネットワーク、クラウド音声ワークロードを構成します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a91a57a077db38675a62238289ad2c204040a9cd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675439"
---
# <a name="prepare-my-service"></a>サービスを準備する

この記事では、組織のクラウド 音声サービスを準備するための要件の概要について説明します。 適切な準備をすることで、組織にクラウド音声機能を提供する準備ができていることを確認できます。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Microsoft Teams音声ワークロードのオンボーディング チェックリスト

次のチェックリストでは、Microsoft Teamsで電話会議、通話プラン ("通話プラン")、および電話システムダイレクト ルーティング ("ダイレクト ルーティング") 機能を使用して電話システムする手順について説明します。

*  [TeamsのMicrosoft 365またはOffice 365を準備する](onboarding-checklist-enable-office-365.md)

*  [コア機能Teams構成する](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [ネットワークを準備する](prepare-network.md)

*  [Teamsでクラウド音声ワークロードを構成する](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Teamsでのダイレクト ルーティングの構成](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

これらのチェックリストのタスクとアクティビティは、Teamsを使用したクラウド音声機能のすべてのデプロイに適用される主要な "to Do" 項目です。 チェックリストをカスタマイズして、独自のTeams体験に固有のアクティビティとタスクを含めることができます。

>[!NOTE]
>このガイダンスは、通話プラン、電話会議、およびダイレクト ルーティングのみに焦点を当てています。 Teamsを初めて使用する場合は、[Microsoft Teamsの概要を](teams-overview.md)確認してください。 Teams展開を計画するための一般的なガイダンスについては、[Microsoft Teamsでのチャット、チーム、チャネル、アプリのデプロイ](deploy-chat-teams-channels-microsoft-teams-landing-page.md)から始めます。

提供されたチェックリストを使用して、個々のアクティビティとタスクの状態を追跡し、重要な手順をスキップしていないことを確認します。 各アクティビティには、必要なアクションの詳細な説明と、そのアクティビティを完了するために使用できる追加情報への参照が含まれています。

チェックリストを順番に従うことをお勧めしますが、正確なシーケンスは、デプロイの範囲と環境の構成と複雑さによって異なります。 "greenfield" Teamsデプロイ (以前の Skype for Business Online プレゼンスのないデプロイ) または Skype for Business Online から Teamsへの移行をサポートするように編成されています。 Skype for Business Online から移行する場合は、これらのアクティビティの一部が既に完了しており、現在は無視できます。

サイトごとにユーザーをオンボードする場合は、これらのチェックリストの補足ガイドとして、 [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) を使用することを強くお勧めします。

>[!NOTE]
>構成設定のほとんどは、Teamsと Skype for Business Online の間で一般的です。 Microsoft 365 管理 センターとMicrosoft Teams管理センターを使用して、これらの設定を構成します。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>オンボーディング チェックリストの完了を監督する責任はWhoですか?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次のステップ</td><td><ul><li>オンボード チェックリストをダウンロードします。</li><li>組織の展開計画に従って、オンボード チェックリスト項目を段階的に実行します。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>オンボーディングを続行する

これらのチェックリストを完了すると、Teamsデプロイに音声機能が正常に追加されます。

次の手順として、 [Site Enablement Playbook for Voice (Playbook) を](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 使用して、各サイトにユーザーをオンボードし、重要なサイト固有のアクティビティを計画して実行できるようにします。

-   サイト別の準備完了サイトロールアウト計画

-   サービス管理プロセスを確立する

-   テストと修復を実行する

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Teamsでクラウド音声ワークロードをテストする

Teamsクラウド 音声ビジネスの成功と技術的な実装計画を構想フェーズの一部として定義して文書化し、管理センターで必要な構成を実行したら、次の手順は、機能、機能、使いやすさを通じて組織の期待と要件が満たされていることを検証することです。 運用環境にパイロットまたは最終デプロイをデプロイする前に、この検証手順を実行する必要があります。

構想フェーズで定義したビジネス成功計画を活用して、テスト フェーズ中に評価されるアクティビティ、期待値、機能/機能テスト ケース、および全体的なスコープを決定するための基礎として機能します。

## <a name="define-your-testing-approach"></a>テスト アプローチを定義する

最も簡単な形式では、テスト アプローチは、電話会議、通話プラン、またはダイレクト ルーティング サービスの機能を確認し、スコープ内のユーザーに対して機能要件が満たされていることを確認するためのテスト計画を開発することに基づいています。 電話会議の実装のオンボード フェーズのテスト計画の例を次に示します。


| テストする電話会議機能 | 結果の概要 | その他の注意事項 |
|------------|-----------------|------------------|
| 電話会議ダイヤルイン情報を含むアドホック Teams会議をスケジュールする | 成功/失敗   | TBD |
| ダイヤルイン情報を提供して PSTN から会議にダイヤルインして、会議の音声に電話を使用する | 成功/失敗 | TBD |
| PSTN 経由でダイヤルアウトして、他のユーザーを既存の会議に参加させる | 成功/失敗 | TBD |



| プランまたはダイレクト ルーティング機能を呼び出してテストする | 結果の概要 | その他の注意事項 |
|----------------------------------------------------|-----------------|------------------|
| PSTN 番号をダイヤルして PSTN 通話を行う       | 成功/失敗       | TBD |
| 外部回線 (モバイル、固定電話) から PSTN 番号をダイヤルして PSTN 通話を受信する | 成功/失敗 | TBD|
| あるTeams ユーザーから別のユーザーに PSTN 通話を転送する | 成功/失敗 | TBD |


>[!TIP]
>テスト ケースの作成を開始点として支援するには、[Teams会議と通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)で利用できるユーザー ガイダンスの一覧を参照してください。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Teamsのクラウド音声ワークロードを設定する

テスト アプローチを定義したので、次の手順では、クラウド音声機能のスコープ内でサービス環境とユーザー Teams構成します。

詳細については、次を参照してください。

- [音声会議での電話会議の計画  ](./cloud-voice-landing-page.md)

- [Microsoft Teams の電話会議を設定する](set-up-audio-conferencing-in-teams.md)

- [通話プランを使用した電話システムの技術計画](calling-plan-landing-page.md)

- [Skype for BusinessとMicrosoft Teamsの通話プランを設定する](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [ダイレクト ルーティングを計画する](./direct-routing-plan.md)

- [ダイレクト ルーティングを構成する](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>テスト計画を実行する

[//]: # (編集は問題ありませんか?"User" は少しあいまいに思えました。)
ユーザー環境とサービスが構成された後、テストの最後の手順には、機能と機能の検証に重点を置いたテスト計画の実行が含まれます。 

**電話会議、スコープ内のユーザーとサイトの前提条件と前提条件をテストします。**

-   電話会議 サービスのビジネス ユース ケース定義が完了しました。

-   電話会議に必要なライセンスが利用可能であり、割り当てられています。

-   組織サイトとユーザー グループの一覧が識別されました。

-   言語設定を使用して、専用および共有の電話会議ダイヤルイン番号の一覧が識別され、構成されています。

-   [コミュニケーション クレジット](what-are-communications-credits.md) (必要な場合) は、組織に対して設定されています。

-   電話会議会議ブリッジの設定が識別され、構成されています (PIN の長さ、入退室通知、有効化通知の設定)。

-   電話会議ダイヤルアウト シナリオをサポートするテナント会議ポリシーとダイヤル プランの設定は、識別、構成、および適用されています。

-   電話会議コンプライアンス要件が特定され、構成されています。

**スコープ内のユーザーとサイトの前提条件と前提条件をテストするプランの呼び出し:**

-   通話プラン サービスのビジネス ユース ケース定義が完了しました。

-   通話プランに必要なライセンスが利用可能であり、割り当てられています。

-   組織サイトとユーザー グループの一覧が識別されました。

-   ユーザーに割り当てる電話番号は、Microsoft に取得または移植されており、テナント ポータルで使用できます。

-   [コミュニケーション クレジット](what-are-communications-credits.md) (必要な場合) は、組織に対して設定されています。

-   通話プランのシナリオをサポートするテナント ユーザー ポリシーとダイヤル プランの設定は、識別、構成、および適用されています。

-   通話プランのコンプライアンス要件が特定され、構成されています。

**スコープ内のユーザーとサイトのダイレクト ルーティング テストの前提条件と前提条件:**

-   ダイレクト ルーティング サービスのビジネス ユース ケース定義が完了しました。

-   直接ルーティングに必要なライセンスが使用可能であり、割り当てられています。

-   組織サイトとユーザー グループの一覧が識別されました。

-   [認定されたセッション ボーダー コントローラー (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) がデプロイされ、構成され、電話システムとペアになっています。

-   Enterprise音声が有効になっており、電話番号が割り当てられています。

-   音声ルーティング ポリシーが識別され、構成され、割り当てられています。

-   Microsoft Teamsは、スコープ内のユーザーの優先呼び出しクライアントとして設定されています。
 
-   ダイレクト ルーティングコンプライアンス要件が特定され、構成されています。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>デプロイする機能の電話会議を決定します (サービスの決定)。</li><li>電話会議のユーザー機能要件を特定します。</li><li>電話会議のサービス構成要件を特定します。</li><br><li>ダイレクト ルーティングプランと通話プランのどちらを展開して構成するかを決定します。<li>デプロイする機能の電話システムを決定します (サービスの決定)。</li><li>プランの呼び出しまたは直接ルーティングのユーザー機能要件を特定します。</li><li>プランの呼び出しまたは直接ルーティングのサービス構成要件を特定します。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次のステップ</td><td><ul><li>テスト計画のアプローチを開発して文書化します。</li><li>電話会議機能のスコープ内でサービス環境とユーザーを準備します。</li><li>プランの呼び出しまたはダイレクト ルーティング機能のスコープ内で、サービス環境とユーザーを準備します。</li><li>有効にする電話会議機能のテスト検証を実行します。</li><li>有効にする通話プランまたはダイレクト ルーティング機能のテスト検証を実行します。</li><li>テスト エラーが発生した場合は、構成が正しいことを確認し、コミュニティの記事を確認し、必要に応じてサポート ケースを作成します。</li></ul></td></tr>
</table>


Teamsで電話会議のテストを実行する方法の詳細なガイダンスについては、電話会議[の詳細なテスト ガイドを](./deploy-audio-conferencing-teams-landing-page.md)参照してください。

Teamsでプランを呼び出すためのテストを実行する方法の詳細なガイダンスについては、電話システム[の詳細なテスト ガイドを](./cloud-voice-landing-page.md)参照してください。

<!--ENDOFSECTION-->