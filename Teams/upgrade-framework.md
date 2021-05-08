---
title: アップグレード フレームワークについて - Skype for BusinessのTeams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 実績のある成功フレームワークを使用して、組織のアップグレード体験をSkype for BusinessからTeams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78215457177689b549112a19a9477fdd01c91de2
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282514"
---
# <a name="about-the-upgrade-framework"></a>アップグレードのフレームワークについて

アップグレードのプロセスから推測を取り出す助けとして、変更を実装するための実証済みのフレームワークを採用しました。 以下に示す通り、フレームワークの各ステップは前の手順に基が構築され、最適な結果を得る場合は、手順を順番に実行することをお勧めします。  

まず、適切な関係者を集め、アップグレード計画 (スコープ、目標、タイムラインなど) を定義します。 計画が整った状態で、技術環境とエンド ユーザーが準備ができていることを確認Teams。 次に、準備が整った段階でアップグレードを実装し、パイロットから組織全体のアップグレードに移行します。 組織が運用を開始したらTeams品質を監視し、ユーザーの導入を加速する運用計画を確立します。

![アップグレード体験フレームワークの図](media/upgrade-banner-main.png "プロジェクトが適切なプロジェクト チームで成功するために設定されている必要があります。プロジェクトの範囲、目標、タイムラインを定義します。技術的な準備とユーザーの準備の両方を確認します。ロールアウト計画を実行します。結果を最大化する勢いを維持します。")

アップグレード プロセスの場所を特定するには、関連するページでこのフレームワークのグラフィックを探します。

## <a name="sample-upgrade-timeline"></a>アップグレードタイムラインのサンプル

アップグレードの体験は、変更の計画を開始すると開始されます。 成功フレームワークをガイドラインとして活用すると、アップグレード前のフェーズからアップグレードの計画と準備を行う段階から、アップグレード後の運用フェーズに移動し、結果を維持および増幅するように設計されたサンプル タイムラインを次に示します。 

> [!NOTE]
> Teams への取り組みには、複数のモードを活用 [](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)し、異なる時間にユーザー のグループをアップグレードする必要がある場合があります。この場合、Teams で勢いを維持しながら、ユーザーのアップグレード エクスペリエンスを制御できます。    

アップグレード体験がどのように展開される可能性があるのかについて説明するために、以下のサンプル プランを提供しました。このプランでは、Skype for Business Online から Islands モードから Teams までの体験のみを定義しています。 さらに、サンプル プランでは、ユーザーを 4 つのアップグレード グループ (コーホート) に分割した組織の概要を示します。 これをテンプレートとして使用して、使用するさまざまなモードと、ユーザーをセグメント化するアップグレード グループの数を組 [](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)み込み、Teams への特定の体験を含むプランをカスタマイズ   します。 

## <a name="pre-upgrade"></a>アップグレード前

**を使用するために組織をTeams。** アプリケーションへのアップグレードを成功にTeams、準備のための十分な時間を割り当てる必要があります。 組織が Teams の価値をすぐに実現できるだけでなく、Teams の準備が整い次第、Skype for Business からのアップグレードを加速できます。 Skype for Business と共に Teams を既に有効にしている場合は、これらのアップグレード前のアクティビティをチェックポイントとして使用して、ユーザーを Teams にアップグレードする前に、組織の準備状況を検証します。 

> [!TIP]
> アップグレード プロジェクト [のサンプル 計画](https://aka.ms/UpgradeSuccessKit)とパイロット テスト計画に加えて、コミュニケーションやユーザーアンケートなどのテンプレート ユーザー対応資料用のアップグレード成功キット   をダウンロードします。 キットで利用可能な項目は、次の一覧にアスタリスク (*) でマークされます。

### <a name="plan-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>計画: 組織が長期的な成功を収めるのに役立つアップグレード 計画を作成する

| ステップ |  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **関係者を定義する** | アップグレードの成功を推進する責任をプロジェクト チーム メンバーに割り当てる。 | [関係者を参加する](upgrade-enlist-stakeholders.md) |
| **2** | **プロジェクトのビジョンと範囲を定義する** | "大きな画像" のビジョンと現在のプロジェクト スコープを設計して、アップグレード体験のブループリントを作成します。 | [Projectビジョン](upgrade-define-project-scope.md#project-vision) <br> <br>[Project スコープ](upgrade-define-project-scope.md#project-scope) |
| **3** | **プロジェクトの目標を定義する** | 進捗状況とプロジェクトの成功を測定できる目標を設定します。 | [Project目標](upgrade-define-project-scope.md#project-goals) |
| **4** | **リスクと軽減計画を特定する** | 問題が発生した場合にプロジェクトをすばやく追跡し戻す軽減計画を確立します。 | [リスクと軽減策](upgrade-define-project-scope.md#risks-and-mitigation) |
| **5** | **タイムラインを定義する** | タイムラインと重要なマイルストーンを設定して、プロジェクトを時間と予算に合った時間で管理できます。 | [タイムライン](upgrade-define-project-scope.md#timeline) <br><br> [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **6** | **アップグレードと共存Skype for Business適切Teamsを定義する** | 体験をマップして、組織に最適Skype for BusinessからTeamsパスを確認します。 | [Microsoft Teams と Skype for Business の共存と相互運用性を理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br><br>[PSTN 電話システムオプションについて](cloud-voice-landing-page.md)<br><br>  [アップグレードの行程を選択する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) |


### <a name="prepare-evaluate-your-organizations-readiness-for-teams"></a>準備: 組織の準備を評価Teams

| ステップ |  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **環境を評価し、技術的なオンボードTeams完了する** | ユーザー エクスペリエンスを最適化し、Teamsアップグレードを容易にするのに役立つ、環境の準備ができていることを確認します。 | [にアップグレードする前に環境をTeams。](upgrade-plan-journey-evaluate-environment.md)<br><br> [サービスをアップグレードする準備をTeams](upgrade-prepare-environment-prepare-service.md) |
| **2** | **リアルタイム メディア シナリオTeamsネットワークを最適化する** | 音声、ビデオ、または会議を展開する場合は、これらの追加の手順を実行して、その機能に合ったネットワークを最適化します。 | [Teams にアップグレードするためにネットワークを準備する](prepare-network.md) |
| **3** | **組織の変更の準備状況を評価し、チームワーク シナリオを定義する** | ユーザー ベースを理解し、適切な価値のメッセージングと教育レベルを準備し、ユーザーの導入を促進し、加速します。 | [組織の変更の準備](upgrade-org-change-readiness.md#organizational-change-readiness) |
| **4** | **ユーザーのコミュニケーション、トレーニング、サポートの方法を定義するユーザー準備計画を準備する** | 通信、トレーニング、サポートプランをカスタマイズして、新しいテクノロジへの最適な受け入れ性を確保します。 | [ユーザーの研修計画を準備する](upgrade-user-readiness.md)<br><br>[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **5** | **保留中のアプリの起動を通知Microsoft Teams** | ユーザーが含まれていると感じ、混乱を減らし、興奮を生み出すのを助けるために、早い段階でコミュニケーションを取る。 | [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **6** | **IT スタッフを準備Teams** | 技術スタッフとサポート スタッフが準備に必要なすべてを備え、お客様の技術環境をサポートTeams。 | [IT スタッフを準備Microsoft Teams](upgrade-prepare-it-pros.md) <br><br> [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |

### <a name="pilot-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>パイロット: パイロットを実行して、組織の準備ができていることを確認し、最適な体験を通知Teams

| ステップ |  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **パイロット ロジスティックの概要** | 正式なパイロット ロジスティックを定義して、アップグレードまたは共存する組織の準備を検証します。 | [パイロット ロジスティックの概要](pilot-essentials.md#1-outline-pilot-logistics) |
| **2** | **パイロット参加者を選択し、シナリオをテストする** | チームワーク シナリオの検証と準備の確認に役立つTeams特定します。 | [パイロット参加者を選択し、シナリオをテストする](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
| **3** | **テスト計画とフィードバックアンケートを設計する** | 参加者が完了するための明確に定義されたタスクと、参加者がフィードバックを共有する方法を特定します。 | [テスト計画とフィードバックアンケートを設計する](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
| **4** | **パイロット通信計画を作成する** | パイロット参加者に、何が起こっているか、いつ、なぜ、何が期待されるのかを教育します。 | [通信プランを作成する](pilot-essentials.md#4-create-your-communications-plan)<br><br>[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **5** | **パイロットを実施する** | パイロットを開始し、進行状況を追跡し、必要に応じて反復処理して、パイロット結果を最適化します。 | [パイロットを実施する](pilot-essentials.md#5-conduct-your-pilot) |
| **6** | **学習を評価し、進む計画を評価する** | ユーザーフィードバック、ネットワーク統計、および目標に対する分析のためのサポート チケットを収集し、進む計画を決定します。 | [学習を評価し、進む計画を評価する](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan)

### <a name="deploy-run-teams-in-coexistence-with-skype-for-business"></a>デプロイ: Teamsと共存して実行Skype for Business

| ステップ |  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **新しいアプリの正式な発売をTeams** | 準備ができたら、公式の発表を送信して、Teams勢いを生み出します。 | [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **2** | **アップグレードを実装する** | 実行する手順は、現在のデプロイ環境によって異Skype for Business。 | [アップグレードを実装する](upgrade-to-teams.md) |
| **3** | **新しいロードマップに関するTeamsする** | 組織がTeams移行する適切な時間を特定するには、ロードマップを監視Teams。 | [Teamsロードマップ](https://aka.ms/teamsroadmap) |
| **4** | **追加の通信を送信し、Teamsに参加して、新しいチームの興奮と導入を促進Teams** | ユーザーの導入を促し、継続的なコミュニケーションとチャンピオンとのTeamsの興奮を維持します。 | [Microsoft 365チャンピオン プログラム](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>Upgrade 

**正式な移行を行Teams。** ユーザーをアップグレードする場合は、そのユーザーを Teamsに移動します。 Teams、会議、通話、コラボレーションのプライマリ アプリになり、アプリへのアクセスSkype for Business無効になります。 このフェーズの技術的な側面は非常に単純ですが、変更がユーザー エクスペリエンスに及ぼす影響を考慮し、ユーザーがアクティビティを Skype for Business から Teams に正式に移行できる時間を与えます。 クライアントごとに異なるエクスペリエンスを持つユーザーを減らすには、エンド to エンドのアップグレードウィンドウを 45 日以上に制限してみてください。

### <a name="upgrade-implement-your-upgrade-from-skype-for-business-to-teams"></a>アップグレード: アップグレードからアップグレードSkype for Business実装Teams

| ステップ |  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **上記のアップグレード前のアクティビティが完了したと確認します。** | すべての計画および準備アクティビティの完了を確認することで、アップグレードの成功を保証します。 | 上記のすべて |
| **2** | **最初のアップグレード グループ内のユーザーへの通信を開始する** | アップグレードの開始をユーザーに通知し、プロセス全体を通じて通知を受け取る。 | [ユーザーの研修計画を準備する](upgrade-user-readiness.md) <br><br> [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **3** | **共存モードを有効にして、Teamsグループ内のユーザーに対してのみ有効にする** | 技術ユーザーの移行を実行するにはSkype for Business環境に適した手順に従います。 | [Skype for Business Online から Teams にアップグレードする](upgrade-to-Teams-execute-SkypeforBusinessOnline.md) <br><br>[Skype for Business オンプレミスから Teams にアップグレードする](upgrade-to-Teams-execute-SkypeforBusinessHybridOnprem.md)
| **4** | **ローリング サイクルで、残りのアップグレード グループに対して上記のアップグレード アクティビティを繰り返します。** | 継続的な通信計画を引き続き実行し、計画に基づいてユーザー グループをアップグレードします。 | |
| **5** | **アップグレード後のフィードバックアンケートをすべてのユーザーに送信する** | フィードバックアンケートを使用して、ユーザーからのフィードバックと分析情報を取得します。 | [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>アップグレード後

**を使用してビジネス価値を最大化Teams。** 組織が Teams に完全にアップグレードされた後、目標に対する成功を評価し、前に進む計画を実装します。 

### <a name="operate-measure-the-success-of-your-upgrade"></a>操作: アップグレードの成功を測定する

| ステップ |  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **最初のアップグレードの成功を評価する** | アップグレード前のフェーズで確立した目標に対して進行状況を評価します。 | [Project目標](upgrade-define-project-scope.md#project-goals) |
| **2** | **追跡されていない目標に対して軽減計画を実装する** | 達成されていない目標の軽減策またはコース修正戦略を定義します。 | [Project目標](upgrade-define-project-scope.md#project-goals) |
| **3** | **ネットワークの健全性と品質の監視** | 品質チェックと監視計画を実装して、肯定的なユーザー エクスペリエンスを確保し、サポート デスクへの呼び出しを減らします。 | [ネットワークの健全性と品質の監視](continue-journey.md#monitor-for-network-health-and-quality) |
| **4** | **ユーザーの機運と導入を促進する** | 継続的な導入計画により、ユーザーの導入を促し、Teamsに向け興奮を維持します。 | [ユーザーの機運と導入を促進する](continue-journey.md#drive-user-momentum-and-adoption) |
| **5** | **新しい機能に対して準備する** | 新しいイノベーションと製品改善のための変更サイクルを確立することで、最大値を実現します。 | [新しい機能に対して準備する](continue-journey.md#prepare-for-new-functionality)


> [!Note]
> アップグレード コンテンツは絶えず進化しています。 必ず最新のガイダンスを確認し、次のブログ[をTeamsしてください](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)。 

> [!Important]
> Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。それ以降、アクセスとサポートが終了します。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。 アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。