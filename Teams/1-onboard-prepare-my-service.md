---
title: クラウドボイスサービスの展開を準備する
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: オンボードのチェックリストを使用して、チーム用に Microsoft 365 または Office 365 を準備し、Teams のコア機能、ネットワーク、およびクラウド音声のワークロードを構成します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3c805e8ff14ddb1c46f83db819c5dd8a2c305914
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610069"
---
# <a name="prepare-my-service"></a>サービスを準備する

この記事では、組織のクラウド音声サービスを準備するための要件の概要を示します。 適切に準備しておくと、クラウドの音声機能を組織に提供する準備ができているかどうかを確認できます。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Microsoft Teams の音声ワークロードのオンボードチェックリスト

次のチェックリストは、Microsoft Teams の電話会議、電話システム (以下、「通話プラン」)、電話システムダイレクトルーティング (以下、「直接ルーティング」) 機能を実装するための手順を説明しています。

*  [Microsoft 365 または Office 365 をチーム用に準備する](onboarding-checklist-enable-office-365.md)

*  [Teams のコア機能を構成する](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [ネットワークを準備する](prepare-network.md)

*  [Teams でクラウド音声のワークロードを構成する](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Teams で直接ルーティングを構成する](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

これらのチェックリストのタスクとアクティビティは、チームとのクラウド音声機能のすべての展開に適用される "to do" のコア項目です。 このチェックリストをカスタマイズして、自分のチームの旅に固有のアクティビティとタスクを含めることができます。

>[!NOTE]
>このガイダンスは、通話プラン、電話会議、直接ルーティングにのみ焦点を当てています。 チームを初めてお使いになる場合は、 [「Microsoft teams の概要」](teams-overview.md)を参照してください。 チーム展開の計画に関する一般的なガイダンスについては、「 [Microsoft teams でのチャット、チーム、チャネル、アプリの展開](deploy-chat-teams-channels-microsoft-teams-landing-page.md)」をご覧ください。

該当するチェックリストを使用して、個々のアクティビティとタスクの状態を追跡し、クリティカルステップをスキップしていないことを確認します。 各アクティビティには、必要なアクションの詳細な説明と、そのアクティビティを完了するために使用できる追加情報への参照が含まれています。

チェックリストは順番に従うことをお勧めしますが、正確な順序は展開の範囲と環境の構成と複雑さによって異なります。 これらのユーザーは、"から始め" Teams の展開 (以前の Skype for Business Online プレゼンスがないもの) または Skype for Business Online から Teams への移行のいずれかをサポートするように開催されています。 Skype for Business Online から移行している場合は、これらのアクティビティの一部を既に完了している可能性があります。これを無視することができます。

サイトベースでユーザーをオンにしている場合は、これらのチェックリストのガイドとして、[サイトの有効化のためのプレイリスト (プレイリスト)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用することを強くお勧めします。

>[!NOTE]
>ほとんどの構成設定は、Teams と Skype for Business Online で共通です。 これらの設定を構成するには、Microsoft 365 管理センターと Microsoft Teams 管理センターを使用します。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>オンボードチェックリストの完了を監督する担当者を教えてください。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次の手順</td><td><ul><li>オンボードチェックリストをダウンロードします。</li><li>組織の展開計画に従って、オンボードのチェックリスト項目を段階的に操作します。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>オンボードを続行する

これらのチェックリストを完了すると、音声機能がチーム展開に正常に追加されます。

次の手順として、お客様が各サイトでの使用を計画し、サイト固有の重要なアクティビティを計画して実行できるように、[音声 (プレイブック) 向けのサイト支援プレイブック](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用します。

-   サイトロールアウトプランごとの準備が完了しました

-   サービス管理プロセスを確立する

-   テストと修復を実行する

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Teams でクラウドの音声ワークロードをテストする

チームクラウドの音声ビジネスの成功と技術の実装計画を定義して、管理センターで必要な構成を実施した後は、次の手順として、組織の期待と要件が機能、機能性、ユーザビリティによって満たされていることを検証します。 パイロットまたは最終的な展開を運用環境に展開する前に、この検証手順を実行する必要があります。

ビジョン化フェーズで定義したビジネス成功計画を活用して、アクティビティ、期待、機能/機能テストケース、およびテストフェーズで評価される全体的な範囲を決定するための基礎として使用できます。

## <a name="define-your-testing-approach"></a>テスト方法を定義する

最も簡単な方法として、テスト方法は、電話会議、通話プラン、または直接ルーティングサービスの機能を確認して、範囲内のユーザーに対して機能要件が満たされていることを確認するためのテスト計画を策定することに基づいています。 以下は、電話会議の実装のオンボードフェーズのテスト計画の例です。


| テストする電話会議機能 | 結果の概要 | 追加のメモ |
|------------|-----------------|------------------|
| 電話会議のダイヤルイン情報が含まれる臨時の Teams 会議のスケジュールを設定する | 合格/不合格   | TBD |
| 音声会議に電話を使用するには、対応する PSTN からの会議にダイヤルイン情報を入力します。 | 合格/不合格 | TBD |
| PSTN 経由でダイヤルアウトして、他のユーザーを既存の会議に参加する | 合格/不合格 | TBD |



| テストのための通話プランまたはダイレクトルーティング機能 | 結果の概要 | 追加のメモ |
|----------------------------------------------------|-----------------|------------------|
| PSTN 番号にダイヤルして PSTN 通話を行う       | 合格/不合格       | TBD |
| 外部の回線 (携帯電話、固定電話) から PSTN 番号をダイヤルして、PSTN 通話を受信します。 | 合格/不合格 | TBD|
| 1つの Teams ユーザーから別のユーザーに PSTN 通話を転送する | 合格/不合格 | TBD |


>[!TIP]
>開始点としてテストケースの作成を支援するには、 [Teams の会議と通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)で利用できるユーザーガイダンスの一覧を参照してください。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Teams でクラウド音声のワークロードを設定する

テスト方法の定義が完了したら、次の手順では、Teams クラウドボイス機能のスコープ内のサービス環境とユーザーを構成します。

詳細については、以下を参照してください。

- [音声会議での電話会議の計画  ](cloud-voice-deployment.md)

- [Microsoft Teams の電話会議を設定する](set-up-audio-conferencing-in-teams.md)

- [通話プランを使用した電話システムの技術計画](calling-plan-landing-page.md)

- [Skype for Business および Microsoft Teams の通話プランを設定する](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [ダイレクト ルーティングを計画する](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [ダイレクト ルーティングを構成する](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>テスト計画を実行する

[//]: # (編集しますか?"ユーザー" は、自分にとって少々あいまいなものに思われます。)
ユーザー環境とサービスを構成した後、テストの最後のステップには、機能と機能の検証にフォーカスがあるテスト計画の実行が含まれます。 

**電話会議は、スコープ内のユーザーとサイトに関する前提条件と前提条件をテストします。**

-   電話会議サービスのビジネスユースケースの定義が完了しました。

-   電話会議に必要なライセンスはあり、割り当てられています。

-   組織のサイトとユーザーグループの一覧が確認されました。

-   専用の電話会議のダイヤルインの一覧と言語の優先順位が設定されています。

-   組織に対して[通信クレジット](what-are-communications-credits.md)(必要な場合) が設定されている。

-   電話会議のブリッジの設定が識別され構成されている (PIN の長さ、エントリ/終了の通知、有効化通知の設定)。

-   電話会議のダイヤルアウトシナリオをサポートするテナント会議のポリシーとダイヤルプランの設定が、特定、構成、適用されている。

-   電話会議のコンプライアンス要件を特定して構成しました。

**通話プラン: スコープ内のユーザーとサイトの前提条件と前提条件をテストします。**

-   通話プランサービスのビジネスユースケースの定義が完了しました。

-   通話プランのライセンスが必要であり、割り当てられています。

-   組織のサイトとユーザーグループの一覧が確認されました。

-   ユーザーに割り当てられる電話番号は、Microsoft に取得または移植されたため、テナントポータルで利用できます。

-   組織に対して[通信クレジット](what-are-communications-credits.md)(必要な場合) が設定されている。

-   通話プランのシナリオをサポートしているテナントのユーザーポリシーとダイヤルプランの設定が、特定、構成、適用されている。

-   通話プランのコンプライアンス要件は、確認および構成されています。

**スコープ内のユーザーとサイトに対する直接ルーティングテストの前提条件と前提条件:**

-   ダイレクトルーティングサービスのビジネスユースケースの定義が完了しました。

-   直接ルーティングのために必要なライセンスは利用可能であり、割り当てられています。

-   組織のサイトとユーザーグループの一覧が確認されました。

-   [認定セッションボーダーコントローラー (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)は、電話システムとの組み合わせ、構成、およびペアリングされています。

-   エンタープライズボイスが有効になり、電話番号が割り当てられました。

-   音声ルーティングポリシーは、識別、構成、割り当てされています。

-   Microsoft Teams は、範囲内のユーザーの優先発信クライアントとして設定されています。
 
-   直接ルーティングのコンプライアンス要件が識別され、構成されている。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>判断ポイント</td><td><ul><li>どの電話会議機能を展開するかを決定します (サービス決定)。</li><li>電話会議のユーザー機能要件を特定します。</li><li>電話会議のサービス構成要件を特定します。</li><br><li>ダイレクトルーティングまたは通話プランを展開して構成するかどうかを決定します。<li>どの電話システム機能が展開されるかを決定します (サービス決定)。</li><li>プランまたはダイレクトルーティングのためのユーザー機能要件を特定します。</li><li>プランまたはダイレクトルーティングのサービス構成要件を特定します。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次の手順</td><td><ul><li>テスト計画のアプローチを開発し、文書化します。</li><li>電話会議機能のスコープでサービス環境とユーザーを準備します。</li><li>プランまたはダイレクトルーティング機能の対象となるように、サービス環境とユーザーを準備します。</li><li>有効にする電話会議機能のテストの検証を実行します。</li><li>有効にする通話プランまたはダイレクトルーティング機能に対してテストの検証を実行します。</li><li>テストの失敗については、構成が正しいことを確認し、コミュニティの記事を確認し、必要に応じてサポート案件を提起します。</li></ul></td></tr>
</table>


Teams で電話会議のテストを実行する方法の詳細については、「[電話会議の詳細なテストガイド](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)」を参照してください。

Teams での通話プランのテストを実行する方法の詳細については、「[電話システムの詳細なテストガイド](onboarding-test-plan-for-enterprises-Phone-System.md)」を参照してください。

<!--ENDOFSECTION-->
