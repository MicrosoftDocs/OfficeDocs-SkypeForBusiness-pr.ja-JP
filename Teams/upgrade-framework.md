---
title: アップグレード フレームワークについて - TeamsへのSkype for Business
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 実証済みの成功フレームワークを使用して、組織のSkype for BusinessからTeamsへのアップグレードを支援します。
ms.localizationpriority: medium
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
ms.openlocfilehash: 0cfc8a3855da45b80ac5cd97d273b9f6c1d90ded
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681968"
---
# <a name="about-the-upgrade-framework"></a>アップグレードのフレームワークについて

アップグレードの過程から推測を取り消すために、変更を実装するための実証済みのフレームワークが採用されています。 次に示すように、フレームワークの各ステップは、前の手順に基づいて構築され、最適な結果を得るために、手順に従って順番に実行することをお勧めします。  

まず、適切な利害関係者を集め、アップグレード計画 (スコープ、目標、タイムラインなど) を定義します。 計画を立て、技術環境とエンド ユーザーがTeamsの準備ができているかどうかを確認します。 次に、準備ができたらパイロットから組織全体のアップグレードに移行して、アップグレードを段階的に実装します。 組織がTeamsになったら、品質を監視し、ユーザーの導入を加速する運用計画を確立します。

![アップグレード体験フレームワークの図。](media/upgrade-banner-main.png "適切なプロジェクト チームでプロジェクトが成功するように設定されていることを確認します。プロジェクトのスコープ、目標、タイムラインを定義します。技術的な準備とユーザーの準備の両方を確認します。ロールアウト計画を実行します。結果を最大化するために勢いを維持します。")

関連ページでこのフレームワーク グラフィックを探して、アップグレード プロセスの場所を特定します。

## <a name="sample-upgrade-timeline"></a>アップグレードのタイムラインのサンプル

アップグレードの手順は、変更の計画を開始すると開始されます。 成功フレームワークをガイドラインとして活用すると、アップグレード前のフェーズから、アップグレードを通じてアップグレードの計画と準備を行い、結果を維持および増幅するように設計されたアップグレード後の運用フェーズに移行するサンプル タイムラインを次に示します。 

> [!NOTE]
> Teamsへの道のりには、複数の[モード](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)を活用し、異なる時間にユーザーのグループをアップグレードすることが含まれる可能性があることを理解しています。これにより、Teamsで勢いを維持しながら、ユーザーのアップグレード エクスペリエンスを制御できます。  

アップグレードの体験がどのように展開されるかを示すために、以下に、オンラインモードからアイランド モードSkype for Business Teamsのみの体験を定義するサンプル プランを提供しました。 さらに、サンプル プランでは、ユーザーを 4 つのアップグレード グループ (コホート) に分割した組織の概要を示します。 これをテンプレートとして使用して、Teamsへの特定の移動を包含するように計画をカスタマイズし、使用するさまざまな[モード](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)と、ユーザーをセグメント化するアップグレード グループの数を組み込みます。 

## <a name="pre-upgrade"></a>アップグレード前

**Teamsのために組織を準備します**。 Teamsへのアップグレードを成功させるには、準備に十分な時間を割り当てることが重要です。 組織がTeamsの価値の実現を迅速に開始できるだけでなく、Teamsが準備できたらすぐに、Skype for Businessからのアップグレードを高速化できます。 Skype for Businessと共にTeamsを既に有効にしている場合は、これらのアップグレード前アクティビティをチェックポイントとして使用して、ユーザーをTeamsにアップグレードする前に組織の準備状況を検証します。 

> [!TIP]
> アップグレード プロジェクト 計画とパイロット テスト 計画のサンプルに加えて、コミュニケーションやユーザーアンケートなどのテンプレート ユーザー準備資料用の Upgrade [Success Kit](https://aka.ms/UpgradeSuccessKit) をダウンロードします。 キットで入手できるアイテムには、次の一覧にアスタリスク (*) が付いています。

### <a name="plan-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>プラン: 長期的な成功のために組織が確実に設定されるようにアップグレード計画を作成する

| ステップ |&nbsp;| 概要 | リソース |
|------|--|---------|----------|
| **1** | **利害関係者を定義する** | アップグレードを成功に導く責任をプロジェクト チーム メンバーに割り当てます。 | [利害関係者を参加させる](upgrade-enlist-stakeholders.md) |
| **2** | **プロジェクトのビジョンとスコープを定義する** | "全体像" のビジョンと現在のプロジェクト スコープを設計して、アップグレード体験のブループリントを作成します。 | [Projectビジョン](upgrade-define-project-scope.md#project-vision) <br> <br>[Projectスコープ](upgrade-define-project-scope.md#project-scope) |
| **3** | **プロジェクトの目標を定義する** | プロジェクトの成功だけでなく、進行状況を測定できる目標を設定します。 | [Projectの目標](upgrade-define-project-scope.md#project-goals) |
| **4** | **リスクと軽減策の特定** | 問題が発生した場合にプロジェクトを迅速に軌道に戻すことができる軽減策計画を立てます。 | [リスクと軽減策](upgrade-define-project-scope.md#risks-and-mitigation) |
| **5** | **タイムラインを定義する** | タイムラインと重要なマイルストーンを設定して、プロジェクトを時間と予算に合わせて維持できるようにします。 | [タイムライン](upgrade-define-project-scope.md#timeline) <br><br> [アップグレードサクセス キット](https://aka.ms/UpgradeSuccessKit) |
| **6** | **適切なSkype for BusinessとTeamsアップグレードと共存戦略を定義する** | Skype for Businessから組織のTeamsへの最適なパスを確保するために、体験をマップします。 | [Microsoft Teams と Skype for Business の共存と相互運用性を理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br><br>[電話システムと PSTN 接続オプションについて理解する](cloud-voice-landing-page.md)<br><br>  [アップグレードの行程を選択する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) |


### <a name="prepare-evaluate-your-organizations-readiness-for-teams"></a>準備: Teamsに対する組織の準備状況を評価する

| ステップ |&nbsp;  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **環境を評価し、技術的なオンボーディングTeams完了する** | ユーザー エクスペリエンスを最適化し、時間の経過と共にアップグレードを容易にするために、環境がTeamsの準備ができていることを確認します。 | [Teamsにアップグレードする前に、環境を評価します](upgrade-plan-journey-evaluate-environment.md)。<br><br> [Teamsにアップグレードするためのサービスの準備](upgrade-prepare-environment-prepare-service.md) |
| **2** | **Teams用にネットワークを最適化する(特にリアルタイム メディア シナリオの場合)** | オーディオ、ビデオ、または会議を展開する場合は、これらの追加手順を実行して、その機能に合わせてネットワークを最適化します。 | [Teams にアップグレードするためにネットワークを準備する](prepare-network.md) |
| **3** | **組織の変更の準備状況を評価し、チームワークのシナリオを定義する** | 適切な価値のメッセージングと教育レベルを準備して、ユーザーの導入を容易にし、迅速に進めるために、ユーザー ベースを理解します。 | [組織の変更準備](upgrade-org-change-readiness.md#organizational-change-readiness) |
| **4** | **ユーザーの通信、トレーニング、サポートの方法を定義するためのユーザー準備計画を準備する** | 通信、トレーニング、サポート計画をカスタマイズして、新しいテクノロジに対する最適な受け入れ性を確保します。 | [ユーザーの研修計画を準備する](upgrade-user-readiness.md)<br><br>[アップグレードサクセス キット](https://aka.ms/UpgradeSuccessKit) |
| **5** | **Microsoft Teamsの保留中の起動を発表する** | 早い段階でコミュニケーションを取り、ユーザーが含まれていると感じ、混乱を減らし、刺激を生み出せるようにします。 | [アップグレードサクセス キット](https://aka.ms/UpgradeSuccessKit) |
| **6** | **Teamsの IT スタッフを準備する** | 技術スタッフとサポート スタッフが準備に必要なものをすべて用意し、Teamsの技術環境をサポートしていることを確認します。 | [Microsoft Teamsのために IT スタッフを準備する](upgrade-prepare-it-pros.md) <br><br> [アップグレードサクセス キット](https://aka.ms/UpgradeSuccessKit) |

### <a name="pilot-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>パイロット: パイロットを実行して、組織の準備が整っていることを確認し、最適なTeamsへの道のりを通知します。

| ステップ | &nbsp; | 概要 | リソース |
|------|--|---------|----------|
| **1** | **パイロットロジスティクスの概要** | アップグレードまたは共存する組織の準備を検証するために役立つ正式なパイロット ロジスティクスを定義します。 | [パイロットロジスティクスの概要](pilot-essentials.md#1-outline-pilot-logistics) |
| **2** | **パイロット参加者とテスト シナリオを選択する** | チームワークのシナリオを検証し、準備Teams確認するのに役立つユーザーを特定します。 | [パイロット参加者とテスト シナリオを選択する](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
| **3** | **テスト計画とフィードバックアンケートを設計する** | 参加者が完了するための明確に定義されたタスクと、参加者がフィードバックを共有する方法を特定します。 | [テスト計画とフィードバックアンケートを設計する](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
| **4** | **パイロット通信計画を作成する** | パイロット参加者に、何が起こっているか、いつ、なぜ、何が期待されているのかについて教育します。 | [通信プランを作成する](pilot-essentials.md#4-create-your-communications-plan)<br><br>[アップグレードサクセス キット](https://aka.ms/UpgradeSuccessKit) |
| **5** | **パイロットを実施する** | パイロットを開始し、進行状況を追跡し、必要に応じて反復処理してパイロットの結果を最適化します。 | [パイロットを実施する](pilot-essentials.md#5-conduct-your-pilot) |
| **6** | **学習を評価し、進む計画を評価する** | ユーザーフィードバック、ネットワーク統計、および目標に対する分析のためのサポート チケットを収集し、今後の計画を決定します。 | [学習を評価し、進む計画を評価する](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan)

### <a name="deploy-run-teams-in-coexistence-with-skype-for-business"></a>デプロイ: Skype for Businessと共存してTeamsを実行する

| ステップ |&nbsp;  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **Teamsの正式リリースを発表する** | Teamsの準備ができたら、公式の打ち上げのお知らせを送信することで、刺激と勢いを生み出します。 | [アップグレードサクセス キット](https://aka.ms/UpgradeSuccessKit) |
| **2** | **アップグレードを実装する** | 実行する手順は、Skype for Businessの現在のデプロイによって異なります。 | [アップグレードを実装する](upgrade-to-teams.md) |
| **3** | **Teamsロードマップに関する最新情報を得る** | Teamsロードマップを監視して、組織がTeamsに移行する適切なタイミングを特定します。 | [Teamsロードマップ](https://aka.ms/teamsroadmap) |
| **4** | **追加のコミュニケーションを送信し、Teamsのチャンピオンと関わり、Teamsの刺激と導入を促進する** | 継続的なコミュニケーションとチャンピオンを使用して、ユーザーの導入を促し、Teamsに対する喜びを維持します。 | [Microsoft 365 チャンピオン プログラム](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>Upgrade 

**Teamsに公式に移動** します。 ユーザーをアップグレードするときに、ユーザーをTeamsのみモードに移行します。 Teamsは、チャット、会議、通話、コラボレーションの主要なアプリになり、Skype for Business アプリへのアクセスが無効になります。 このフェーズの技術的な側面は非常に単純ですが、変更がユーザー エクスペリエンスに与える影響を考慮し、ユーザーが自分のアクティビティをSkype for BusinessからTeamsに正式に移行する時間を確保します。 異なるクライアントで異なるエクスペリエンスを持つユーザーを減らすには、エンド ツー エンドのアップグレード期間を 45 日ほどに制限してみてください。

### <a name="upgrade-implement-your-upgrade-from-skype-for-business-to-teams"></a>アップグレード: Skype for BusinessからTeamsへのアップグレードを実装する

| ステップ |&nbsp;  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **上記のアップグレード前アクティビティが完了したことを確認します** | すべての計画と準備アクティビティの完了を確認することで、アップグレードの成功を確実に支援します。 | 上記のすべて |
| **2** | **最初のアップグレード グループ内のユーザーへの通信を開始する** | アップグレードが開始されていることをユーザーに通知し、プロセス全体を通じてユーザーに通知します。 | [ユーザーの研修計画を準備する](upgrade-user-readiness.md) <br><br> [アップグレードサクセス キット](https://aka.ms/UpgradeSuccessKit) |
| **3** | **共存モードを有効にして、最初のアップグレード グループ内のユーザーに対してのみTeamsする** | Skype for Business環境に適した手順に従って、技術的なユーザー移行を実行します。 | [Skype for Business Online から Teams にアップグレードする](upgrade-to-Teams-execute-SkypeforBusinessOnline.md) <br><br>[Skype for Business オンプレミスから Teams にアップグレードする](upgrade-to-Teams-execute-SkypeforBusinessHybridOnprem.md)
| **4** | **ローリング サイクルで残りのアップグレード グループに対して上記のアップグレード アクティビティを繰り返します** | 引き続き継続的な通信プランを推進し、プランに基づいてユーザー グループをアップグレードします。 | |
| **5** | **アップグレード後のフィードバックアンケートをすべてのユーザーに送信する** | フィードバックアンケートを使用して、ユーザーからのフィードバックと分析情報をキャプチャします。 | [アップグレードサクセス キット](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>アップグレード後

**Teamsを使用してビジネス価値を最大化** します。 組織がTeamsに完全にアップグレードされたら、時間を取って目標に対する成功を評価し、勢いを増し続ける計画を実装します。 

### <a name="operate-measure-the-success-of-your-upgrade"></a>操作: アップグレードの成功を測定する

| ステップ | &nbsp; | 概要 | リソース |
|------|--|---------|----------|
| **1** | **初期アップグレードの成功を評価する** | アップグレード前フェーズで確立した目標に対して進行状況を評価します。 | [Projectの目標](upgrade-define-project-scope.md#project-goals) |
| **2** | **順調に進んでいないすべての目標に対する軽減策計画を実装する** | 達成されていない目標の軽減策またはコース修正戦略を定義します。 | [Projectの目標](upgrade-define-project-scope.md#project-goals) |
| **3** | **ネットワークの健全性と品質の監視** | 品質チェックと監視計画を実装して、ユーザー エクスペリエンスを向上させ、サポート デスクへの通話を減らします。 | [ネットワークの健全性と品質の監視](continue-journey.md#monitor-for-network-health-and-quality) |
| **4** | **ユーザーの機運と導入を促進する** | 継続的な導入計画を使用して、ユーザーの導入を促し、Teamsに対する刺激を維持します。 | [ユーザーの機運と導入を促進する](continue-journey.md#drive-user-momentum-and-adoption) |
| **5** | **新しい機能に対して準備する** | 新しいイノベーションと製品の改善のための変更サイクルを確立することで、最大限の価値を実現します。 | [新しい機能に対して準備する](continue-journey.md#prepare-for-new-functionality)


> [!Note]
> アップグレード コンテンツは絶えず進化しています。 最新のガイダンスを確認し、[Teamsブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)を読んでください。 

> [!Important]
> Skype for Business Online は 2021 年 7 月 31 日に廃止されました。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。 アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。