---
title: アップグレード フレームワークについて - Skype for Business から Teams へ
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 実績のある成功フレームワークを使用して、Skype for Business から Teams への組織のアップグレードを支援します。
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
ms.openlocfilehash: 4b73d4d38344952c2b0692939bce9573a16e4155
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122171"
---
# <a name="about-the-upgrade-framework"></a>アップグレードのフレームワークについて

アップグレードの手順から推測を取り出すのを支援するために、変更を実装するための実績のあるフレームワークを採用しました。 次に示すフレームワークの各ステップは、前の手順で構築され、最適な結果を得る場合は、次の手順を順番に実行することをお勧めします。  

まず、適切な関係者をまとめ、アップグレード計画 (スコープ、目標、タイムラインなど) を定義します。 計画を立て、技術環境とエンド ユーザーが Teams の準備ができていることを確認します。 次に、アップグレードを段階で実装し、準備ができたら、パイロットから組織全体のアップグレードに移行します。 組織が Teams に参加したら、品質を監視し、ユーザーの導入を加速する運用計画を確立します。

![アップグレードジャーニー フレームワークの図](media/upgrade-banner-main.png "適切なプロジェクト チームでプロジェクトを成功に向けセットアップします。プロジェクトの範囲、目標、タイムラインを定義します。技術的な準備とユーザーの準備を確認します。ロールアウト計画を実行します。運動量を維持して結果を最大化します。")

アップグレード プロセスの場所を特定するには、関連ページでこのフレームワーク グラフィックを探します。

## <a name="sample-upgrade-timeline"></a>アップグレード タイムラインの例

アップグレードの開始は、変更の計画を開始するときに開始されます。 次に示すのは、アップグレード前のフェーズからアップグレードの計画と準備を行う段階から、アップグレードを通じて、およびアップグレード後の運用フェーズに移動し、結果を維持および拡大するためのサンプル タイムラインです。 

> [!NOTE]
> Teams への取り組みには、複数のモード [](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)を活用し、異なる時間にユーザー のグループをアップグレードする必要がある可能性があります。この場合、Teams を使用してユーザー アップグレードエクスペリエンスを制御できます   。  

アップグレードの旅がどのように展開されるのかをご説明するために、Skype for Business Online から諸島モードから Teams への乗り方を定義するサンプル プランを以下に用意しました。 さらに、サンプル プランでは、ユーザーを 4 つのアップグレード グループ (コホート) に分割した組織の概要を示します。 これをテンプレートとして使用して、使用するさまざまなモードと、ユーザーをセグメント化するアップグレード グループの [](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)数を組み込み、Teams への特定の手順を含むプランをカスタマイズします   。 

## <a name="pre-upgrade"></a>アップグレード前

**Teams 用に組織を準備します**。 Teams へのアップグレードを正常に完了するには、準備のための十分な時間を割り当てる必要があります。 組織が Teams の価値をすぐに実現できるだけでなく、Teams の準備が整い次第、Skype for Business からのアップグレードを加速することができます。 既に Skype for Business と一緒に Teams を有効にしている場合は、ユーザーを Teams にアップグレードする前に、アップグレード前のアクティビティを確認し、組織の準備状況を検証します。 

> [!TIP]
> アップグレードプロジェクト [計画とパイロット](https://aka.ms/UpgradeSuccessKit)テスト計画のサンプルに加えて、コミュニケーションやユーザーアンケートなどのテンプレート ユーザー準備資料のアップグレード成功キット   をダウンロードします。 キットで利用可能なアイテムには、次の一覧にアスタリスク (*) が付きます。

### <a name="plan-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>計画: アップグレード計画を作成して、組織が長期的に成功するために設定されるのを支援する

| ステップ |  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **関係者を定義する** | アップグレードの成功を推進する責任をプロジェクト チーム メンバーに割り当てる。 | [関係者を参加する](upgrade-enlist-stakeholders.md) |
| **2** | **プロジェクトのビジョンと範囲を定義する** | "大図" のビジョンと現在のプロジェクト範囲を設計して、アップグレードの計画を作成します。 | [プロジェクトビジョン](upgrade-define-project-scope.md#project-vision) <br> <br>[プロジェクトの範囲](upgrade-define-project-scope.md#project-scope) |
| **3** | **プロジェクトの目標を定義する** | 進捗状況とプロジェクトの成功を測定できる目標を設定します。 | [プロジェクトの目標](upgrade-define-project-scope.md#project-goals) |
| **4** | **リスクと緩和計画を特定する** | リスク軽減計画を立て、問題が発生した場合にプロジェクトをすばやく追跡し戻します。 | [リスクとリスクの軽減](upgrade-define-project-scope.md#risks-and-mitigation) |
| **5** | **タイムラインを定義する** | タイムラインと重要なマイルストーンを設定して、プロジェクトの時間と予算を管理します。 | [タイムライン](upgrade-define-project-scope.md#timeline) <br><br> [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **6** | **Skype for Business と Teams のアップグレードと共存に関する適切な戦略を定義する** | Skype for Business から組織の Teams への最適なパスを確認する方法をマップします。 | [Microsoft Teams と Skype for Business の共存と相互運用性を理解する](teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br><br>[電話システムと PSTN 接続のオプションについて](cloud-voice-landing-page.md)<br><br>  [アップグレードの行程を選択する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) |


### <a name="prepare-evaluate-your-organizations-readiness-for-teams"></a>準備: Teams に対する組織の準備を評価する

| ステップ |  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **環境を評価し、Teams の技術オンボーディングを完了する** | 環境が Teams でユーザー エクスペリエンスを最適化し、時間の変化に合ったアップグレードを容易にする準備ができていることを確認します。 | [Teams にアップグレードする前に環境を評価します](upgrade-plan-journey-evaluate-environment.md)。<br><br> [Teams にアップグレードするためにサービスを準備する](upgrade-prepare-environment-prepare-service.md) |
| **2** | **Teams 用にネットワークを最適化する (特にリアルタイム のメディア シナリオの場合)** | 音声、ビデオ、または会議を展開する場合は、次の追加の手順を実行して、その機能に合ったネットワークを最適化します。 | [Teams にアップグレードするためにネットワークを準備する](prepare-network.md) |
| **3** | **組織の変更の準備を評価し、チームワークシナリオを定義する** | ユーザーの導入を促進および加速するために、適切な価値のメッセージングと教育レベルを準備するためのユーザー ベースを理解します。 | [組織の変更の準備](upgrade-org-change-readiness.md#organizational-change-readiness) |
| **4** | **ユーザーのコミュニケーション、トレーニング、サポートの方法を定義するユーザー準備計画を準備する** | コミュニケーション、トレーニング、サポート計画をカスタマイズして、新しいテクノロジに対する最適な受け入れ性を確保します。 | [ユーザーの研修計画を準備する](upgrade-user-readiness.md)<br><br>[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **5** | **Microsoft Teams の保留中の起動を通知する** | 早期にコミュニケーションを取り、ユーザーが含まれていると感じ、混乱を減らし、ワクワク感を生み出します。 | [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **6** | **IT スタッフを Teams 用に準備する** | テクニカル スタッフとサポート スタッフが準備が整う必要があるすべてを確認し、Teams の技術環境をサポートします。 | [MICROSOFT Teams 用に IT スタッフを準備する](upgrade-prepare-it-pros.md) <br><br> [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |

### <a name="pilot-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>パイロット: パイロットを実行して、組織の準備ができていることを確認し、Teams への最適な旅を知らせる

| ステップ |  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **パイロット 物流の概要** | 正式なパイロット 物流を定義して、アップグレードまたは共存する組織の準備を検証します。 | [パイロット 物流の概要](pilot-essentials.md#1-outline-pilot-logistics) |
| **2** | **パイロット参加者を選択し、シナリオをテストする** | チームワークシナリオを検証し、Teams の準備を確認できるユーザーを特定します。 | [パイロット参加者を選択し、シナリオをテストする](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
| **3** | **テスト計画とフィードバックアンケートを設計する** | 参加者が完了するための明確に定義されたタスクと、参加者がフィードバックを共有する方法を特定します。 | [テスト計画とフィードバックアンケートを設計する](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
| **4** | **パイロット通信計画を作成する** | パイロット参加者に対して、何が起きているか、いつ、なぜ、期待されるのかを教育します。 | [通信プランを作成する](pilot-essentials.md#4-create-your-communications-plan)<br><br>[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **5** | **パイロットを実施する** | パイロットを開始し、進捗状況を追跡し、必要に応じて反復処理してパイロット結果を最適化します。 | [パイロットを実施する](pilot-essentials.md#5-conduct-your-pilot) |
| **6** | **学習を評価し、進む計画を評価する** | ユーザー フィードバック、ネットワーク統計、および目標に対する分析のためのサポート チケットを収集し、進む計画を決定します。 | [学習を評価し、進む計画を評価する](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan)

### <a name="deploy-run-teams-in-coexistence-with-skype-for-business"></a>展開: Skype for Business と共存して Teams を実行する

| ステップ |  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **Teams の正式な立ち上げを発表する** | Teams の準備ができたら、公式発表を送信して、ワクワク感と運動量を生み出します。 | [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **2** | **アップグレードを実装する** | 実行する手順は、Skype for Business の現在の展開によって異なる場合があります。 | [アップグレードを実装する](upgrade-to-teams.md) |
| **3** | **Teams のロードマップに関する情報を得る** | Teams ロードマップを監視して、組織が Teams に移行するのに適切な時間を特定します。 | [Teams のロードマップ](https://aka.ms/teamsroadmap) |
| **4** | **その他のコミュニケーションを送信し、Teams チャンピオンと参加して、Teams のワクワク感と導入を推進する** | 継続的なコミュニケーションとチャンピオンを使用して、Teams のユーザーの導入を促進し、ワクワク感を維持します。 | [Microsoft 365 チャンピオン プログラム](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>Upgrade 

**公式に Teams に移動します**。 ユーザーをアップグレードすると、ユーザーは Teams のみモードになります。 Teams はチャット、会議、通話、共同作業のための主要アプリになり、Skype for Business アプリへのアクセスが無効になります。 このフェーズの技術的側面は非常に単純ですが、変更がユーザー エクスペリエンスに及ぼす可能性がある影響を考慮し、ユーザーがアクティビティを Skype for Business から Teams に正式に移行できる時間を与えます。 クライアントごとに異なるエクスペリエンスを持つユーザーを減らすには、エンドツーエンドのアップグレード ウィンドウを 45 日以上に制限してみてください。

### <a name="upgrade-implement-your-upgrade-from-skype-for-business-to-teams"></a>アップグレード: Skype for Business から Teams へのアップグレードを実装する

| ステップ |  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **上記のアップグレード前のアクティビティを完了したと確認する** | すべての計画と準備のアクティビティの完了を確認して、アップグレードの成功を確実に確保します。 | 上記のすべて |
| **2** | **最初のアップグレード グループのユーザーへの通信を開始する** | アップグレードの開始をユーザーに通知し、プロセス全体を通じてユーザーに通知します。 | [ユーザーの研修計画を準備する](upgrade-user-readiness.md) <br><br> [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **3** | **最初のアップグレード グループのユーザーに対して Teams 専用の共存モードを有効にする** | 技術的なユーザーの移行を実行するには、Skype for Business 環境に適した手順に従います。 | [Skype for Business Online から Teams にアップグレードする](upgrade-to-Teams-execute-SkypeforBusinessOnline.md) <br><br>[Skype for Business オンプレミスから Teams にアップグレードする](upgrade-to-Teams-execute-SkypeforBusinessHybridOnprem.md)
| **4** | **ローリング サイクルで残りのアップグレード グループについて、前のアップグレード アクティビティを繰り返す** | 継続的な通信計画を引き続き進め、プランに基づいてユーザー グループをアップグレードします。 | |
| **5** | **アップグレード後のフィードバックアンケートをすべてのユーザーに送信する** | フィードバックアンケートを使用して、ユーザーからのフィードバックと分析情報を収集します。 | [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>アップグレード後

**Teams を使用してビジネスの価値を最大化します**。 組織が Teams に完全にアップグレードされた後は、時間を取って目標に対する成功を評価し、将来の運動量を継続する計画を実装します。 

### <a name="operate-measure-the-success-of-your-upgrade"></a>操作: アップグレードの成功を測定する

| ステップ |  | 概要 | リソース |
|------|--|---------|----------|
| **1** | **最初のアップグレードの成功を評価する** | アップグレード前のフェーズで設定した目標に対して進捗状況を評価します。 | [プロジェクトの目標](upgrade-define-project-scope.md#project-goals) |
| **2** | **予定されていない目標に対して緩和計画を実装する** | 達成されていない目標の緩和策またはコース修正戦略を定義します。 | [プロジェクトの目標](upgrade-define-project-scope.md#project-goals) |
| **3** | **ネットワークの健全性と品質の監視** | 品質チェックと監視計画を実装して、積極的なユーザー エクスペリエンスを確保し、サポート デスクへの通話を減らします。 | [ネットワークの健全性と品質の監視](continue-journey.md#monitor-for-network-health-and-quality) |
| **4** | **ユーザーの機運と導入を促進する** | 継続的な導入計画を使用して、ユーザーの導入を促進し、Teams のワクワク感を維持します。 | [ユーザーの機運と導入を促進する](continue-journey.md#drive-user-momentum-and-adoption) |
| **5** | **新しい機能に対して準備する** | 新しい技術革新と製品改善のための変更サイクルを確立することで、最大値を実現します。 | [新しい機能に対して準備する](continue-journey.md#prepare-for-new-functionality)


> [!Note]
> アップグレード コンテンツは継続的に進化しています。 最新のガイダンスについては必ず確認し、Teams ブログをお [読みください](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)。 

> [!Important]
> Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。それ以降、アクセスとサポートが終了します。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。 アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。