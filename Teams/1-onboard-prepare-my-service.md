---
title: マイクロソフト チーム クラウドのインターネット電話サービスを展開するための準備します。
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 契約時のチェックリストを使用して、Office 365 をチームに準備し、チームの中心的な機能、ネットワークを構成し、音声のワークロードをクラウドします。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cde789ed0a2c3e6bba56ac1213898a5240d6e81
ms.sourcegitcommit: 57c8211047e6e6501cd1f9eefddfe4da36cb7d7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2018
ms.locfileid: "20302209"
---
# <a name="prepare-my-service"></a>サービスを準備します。

この資料では、音声サービスを組織のクラウドを準備するための要件の概要を示します。 適切に準備するように、クラウドの組織にボイス機能を提供する準備ができていることのことができます。

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>音声のワークロードをマイクロソフトのチームの契約時のチェックリスト

次のチェックリストでは、マイクロソフトのチームでオーディオ会議、電話システム ("呼び出しプラン])、計画を呼び出すと、電話システム直接ルーティング (「直接ルーティング") 機能を実装するため手順を説明します。

*  [Office 365 のチームを準備します。](onboarding-checklist-enable-office-365.md)

*  [チームの中核的な機能を構成します。](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [ネットワークを構成します。](onboarding-checklist-configure-networking.md)

*  [チームで音声のワークロードをクラウドを構成します。](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [チームに直接ルーティングを構成します。](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

タスクとこれらのチェックリストでの作業は、チームと音声機能をクラウドのそれぞれの配置に適用されるコアの"to do"アイテムです。 活動と自分のチームの旅に特有のタスクを含むようにチェックリストをカスタマイズできます。

>[!NOTE]
>このガイドでは、計画を呼び出して、オーディオ会議、および直接ルーティングだけに焦点を当てています。 チームに新しい場合は、[マイクロソフトのチームの概要](teams-overview.md)を確認します。 チーム展開を計画するための一般的なガイダンスは、 [Microsoft のチームの計画ガイド 』](quick-start-enable-teams.md)を参照してください。

個々 のアクティビティとタスクのステータスを追跡するために提供されているチェックリストを使用しの重要な手順をスキップしていないことを確認します。 各アクティビティには、必要なアクションとそのアクティビティを完了するのに使用できるその他の情報への参照の詳細な説明が含まれています。

順序のチェックリストを実行することをお勧めですが、展開と構成のスコープと環境の複雑さの厳密な順序によって異なります。 いずれか、"greenfield"をサポートするために整理されています、チームの配置 (ビジネス オンライン プレゼンスのない以前の Skype で 1 つ) または Skype からチームへのビジネスをオンラインに移行します。 ビジネス オンラインの Skype から移行する場合がすでに完了しているこれらの活動の一部と、それらをここで無視することができます。

サイトごとに契約時のユーザーが表示されたら、以下のチェックリストの補足ガイドとしては、[サイトの有効化の戦略 (戦略) の音声](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用することを強く推奨します。

>[!NOTE]
>ほとんどの構成設定は、チームと Skype のオンライン ビジネスの間で共通です。 これらの設定を構成するのにには、ビジネス管理センターの Office 365 の Skype を使用します。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>意思決定ポイント</td><td><ul><li>契約時チェックリストの完了を監督する責任者がされますか。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>次のステップ</td><td><ul><li>契約時のチェックリストをダウンロードしてください。</li><li>契約時チェックリストの項目の手順に従って、組織の展開計画を使用します。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>契約時を継続します。

これらのチェックリストを完了すると、正常にようになりましたねボイス機能、チームの配置にします。

次の手順では、 [(戦略) の音声をサイトの有効化の戦略](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)を使用してユーザーを支援するオンボードの各サイトと計画し、重要なサイト固有のアクティビティを実行することを防止します。

-   準備ができてサイトごとの展開計画

-   サービス管理プロセスを確立します。

-   テストを実行し、改善策

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>チームでクラウド音声の作業負荷をテスト

定義し Envision フェーズの一部として、チームのクラウド音声ビジネスの成功と技術的な実装計画を文書化して管理センターで必要な構成を行う、次の手順がいることを確認するのには、組織の機能、機能、および利便性を期待し、要件が満たされています。 運用環境でパイロットや最後の展開を展開する前に、この検証の手順を行う必要があります。

テスト段階で評価されるように活動、期待される、機能のテストの場合、および全体的な範囲を決定する基準として使用する Envision フェーズで定義したビジネスの成功プランを利用できます。

## <a name="define-your-testing-approach"></a>テスト アプローチを定義します。

最も単純な形式で、テスト アプローチが、計画を呼び出すには、オーディオ会議の機能を確認する、に基づいてまたはスコープ内のユーザーの機能要件が満たされていることを確認するのには直接ルーティング サービスとテストの開発を計画します。 オンボード オーディオ会議実装のフェーズでの例をテスト計画を次に示します。


| オーディオ会議の機能をテストするには | 結果の概要 | 追加の注記 |
|------------|-----------------|------------------|
| オーディオ会議ダイヤルイン情報を含む特別なチームの会議のスケジュールを設定します。 | 合格/不合格   | 未定 |
| 電話を使用して、提供されているダイヤルイン情報を使用して、PSTN から会議にダイヤルインしてミーティング オーディオの | 合格/不合格 | 未定 |
| PSTN を使用してダイヤルアウトで他のユーザーを既存の会議に参加します。 | 合格/不合格 | 未定 |



| 通話プランまたは直接ルーティング機能をテストするのには | 結果の概要 | 追加の注記 |
|----------------------------------------------------|-----------------|------------------|
| PSTN 番号をダイヤルすることによって、PSTN の呼び出しを行う       | 合格/不合格       | 未定 |
| 外部の行 (モバイル、地上線) から、PSTN の番号をダイヤルすることによって、PSTN の呼び出しを受信します。 | 合格/不合格 | 未定|
| PSTN の呼び出しを別のチームの 1 つのユーザーに転送します。 | 合格/不合格 | 未定 |


>[!TIP]
>開始点として、テスト_ケースの作成を支援するには、[チームの会議や通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)で使用可能なユーザー ・ ガイドの一覧を参照してください。

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>チームの音声のワークロードをクラウドを設定します。

テスト方法を定義した、次の手順、構成、サービスの環境とユーザー チーム クラウドの音声機能のスコープ内です。

詳細についてを参照してください。

- [音声会議での電話会議の計画  ](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [Skype for Business および Microsoft Teams の電話会議のセットアップ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

- [通話プランと電話システムの計画技術](phone-system-with-calling-plans.md#technical-planning-for-phone-system-with-calling-plans)

- [設定計画を呼び出す Skype のビジネスおよびマイクロソフトのチーム](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [直接ルーティングを計画します。](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [直接ルーティングを構成します。](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>テスト計画を実行します。

[//]: # (Ok で編集しますか。「ユーザー」は、自分に少しあいまいな思えました。)
ユーザー環境とサービスを構成すると、テストの最後の手順には、機能と機能の検証でのフォーカスのあるテスト計画の実行が含まれています。 

**電話会議のスコープ内のユーザーとサイトの前提条件をテストします。**

-   ビジネスは、オーディオ会議サービスが完了したケースの定義を使用します。

-   オーディオ会議に必要なライセンス、割り当てられています。

-   組織のサイトとユーザー グループの一覧を指定しています。

-   言語の優先順位の番号にダイヤルを専用または共有の電話会議の一覧を特定して構成します。

-   [通信のクレジット](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)(必要な場合)、組織用に設定されています。

-   オーディオ会議会議ブリッジの設定がされている識別し、(暗証番号 (pin) の長さ、開始/終了の通知、通知の基本設定を有効化) を構成します。

-   テナント会議ポリシーとダイヤル プラン設定の識別、構成、および適用されるアウト ダイヤル シナリオの音声会議をサポートします。

-   オーディオ会議のコンプライアンス要件を特定して構成します。

**通話プランがスコープ内のユーザーとサイトの前提条件をテストします。**

-   ビジネス、呼び出す計画サービスが完了したケースの定義で使用します。

-   計画を呼び出すために必要なライセンス、割り当てられています。

-   組織のサイトとユーザー グループの一覧を指定しています。

-   ユーザーに割り当てられる電話番号を取得またはマイクロソフトとテナント ポータルで利用するように移植されました。

-   [通信のクレジット](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)(必要な場合)、組織用に設定されています。

-   テナント ユーザー ポリシーとダイヤル プランの設定を呼び出すことを計画のシナリオをサポートする識別、構成、および適用。

-   コンプライアンス要件を特定して構成の計画を呼び出します。

**直接ルーティングがスコープ内のユーザーとサイトの前提条件をテストします。**

-   ビジネスでは、直接ルーティング サービスが完了したケースの定義を使用します。

-   直接ルーティングのために必要なライセンス、割り当てられています。

-   組織のサイトとユーザー グループの一覧を指定しています。

-   [セッション ボーダー コント ローラー (SBC) の認定](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs)を導入が構成され、電話システムとペアにします。

-   エンタープライズ ボイスが有効になっていると電話番号が割り当てられています。

-   音声ルーティング ポリシーの識別、構成、および割り当てられています。

-   マイクロソフト チームは、スコープ内のユーザーの優先する呼び出し元クライアントとして設定されています。
 
-   直接ルーティングのコンプライアンス要件を特定して構成します。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>意思決定ポイント</td><td><ul><li>どの電話会議機能を展開するかを決定 (サービスの決定)。</li><li>オーディオ会議のユーザーの機能要件を特定します。</li><li>オーディオ会議サービスの構成要件を特定します。</li><br><li>かどうか直接ルーティングまたはプランを呼び出すことができる展開し、構成を決定します。<li>どの電話システムの機能を配置するかを決定 (サービスの決定)。</li><li>計画を呼び出すか、直接ルーティングのユーザーの機能要件を特定します。</li><li>計画を呼び出すことや、直接ルーティング サービスの構成要件を特定します。</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>次のステップ</td><td><ul><li>開発し、テスト計画のアプローチを文書化します。</li><li>電話会議機能のスコープ内のユーザー、サービスの環境を準備します。</li><li>計画を呼び出すか、直接ルーティング機能のスコープ内のユーザー、サービスの環境を準備します。</li><li>電話会議機能を有効にするためのテストの検証を実行します。</li><li>計画を呼び出すか、直接ルーティング機能を有効にするためのテストの検証を実行します。</li><li>いずれかの障害をテスト、構成が正しいことを確認、コミュニティの記事を確認し、-必要な場合-サポート ・ リクエストを発生させます。</li></ul></td></tr>
</table>


チームでのオーディオ会議のためのテストを実行する方法の詳細なガイダンスが追加は、[オーディオ会議のためのガイドをテストする詳細](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)を参照してください。

チームの計画を呼び出すことでテストを実行する方法に関する追加の詳細については、[電話システムのガイドをテストする詳細](onboarding-test-plan-for-enterprises-Phone-System.md)を参照してください。

<!--ENDOFSECTION-->
