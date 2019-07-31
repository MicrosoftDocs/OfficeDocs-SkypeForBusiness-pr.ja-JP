---
title: Microsoft Teams 向け Pro のアップグレード |ロード
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 大規模な組織の場合、または Skype for Business の展開を大幅にカスタマイズしている場合は、このガイダンスを使用します。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68c2f0f74d1f5f2ba13518c8f56afc1244480a14
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "35934543"
---
# <a name="upgrade-pro"></a>Pro のアップグレード

大規模な組織または Skype for Business の複雑な展開 (ハイブリッドまたはクラウドの音声展開など) 向けに設計されている場合は、Microsoft の実行などのさまざまなアップグレードシナリオと共に、より長いアップグレードのライフサイクルで Pro アカウントをアップグレードします。チームが組織に対応できるようになるまでは、Skype for Business と一緒に teams を利用できます。

次の3つのフェーズに分けて、「Pro のアップグレード」をご覧ください。

|**[アップグレード前](#pre-upgrade)** |**[アップグレード](#upgrade)** |**[アップグレード後](#post-upgrade)** |
|---|---|---|
|Teams の価値を実現する<ul><li>環境の準備</li><li>共同作業、会議、または通話のためにチームを採用する</li><li>Skype for Business から Teams へのアップグレードを計画する</li></ul> |Skype for Business からユーザーを移行する<ul><li>ユーザーに通知して準備する</li><li>ユーザーをチーム専用モードに移動する</li><li>目標に対する使用状況の進捗状況を追跡する</li></ul> | ROI の向上 <ul><li>ネットワークの正常性を監視する</li><li>ユーザーの魅力を維持する</li><li>進行中のチームの革新を計画する</li></ul>|

> [!NOTE]
> チームへの旅には、複数の[モード](https://aka.ms/skypetoteams-coexist)の活用、さまざまなタイミングでのユーザーのグループのアップグレードが含まれていることがわかっています。これにより、チームとの勢いを維持しながら、ユーザーのアップグレードエクスペリエンスを制御することができます。 <br><br>
アップグレード過程がどのように展開されるかを示すために、次のサンプル計画を用意しています。これにより、Skype for Business から**島々**に移動する方法がチームのみになります。 さらに、サンプルの計画では、ユーザーを4つのアップグレードグループまたは_cohorts_に分類した組織の概要を示します。 これをテンプレートとして使用して、チームへの具体的な旅をカバーし、使用しているさまざまな[モード](https://aka.ms/skypetoteams-coexist)とユーザーのセグメント化を行うアップグレードグループの数を組み込み、プランをカスタマイズします。

## <a name="pre-upgrade"></a>アップグレード前

**チームの組織を準備します。** チームへのアップグレードを成功させるためには、準備のために十分な時間を割り当てることが重要です。 組織が Teams の価値をすぐに実感できるだけでなく、チームの準備が整うとすぐに Skype for Business からアップグレードを迅速に開始できるようになります。 チームで計画されている拡張機能の[ロードマップ](https://aka.ms/O365Roadmap)を監視します。これは、組織の適切なアップグレードタイムラインを特定するのに役立ちます。 Skype for Business と共にチームを既に有効にしている場合は、これらのアップグレード前のアクティビティをチェックポイントとして使用して、ユーザーをチームにアップグレードする前に、組織の準備ができていることを確認します。

> [!Tip]
> サンプルアップグレードプロジェクト計画とパイロットテスト計画に加えて、コミュニケーションやユーザーアンケートなどのテンプレートのユーザー準備資料の[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit)をダウンロードします。 このキットで利用可能なアイテムには、以下のリスト\*でアスタリスク () が付いています。

### <a name="days-1ndash7-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>1&ndash;~ 7 日: 組織が長期間の成功を確実に設定できるようにアップグレード計画を作成します。

|ステップ||概要 |設備 |
|---|---|---|---|
|**1** |**関係者を定義する** |プロジェクトの範囲を検討し、技術的な準備とユーザーの準備を通じて関連する関係者を特定して、責任と成功を推進します。 |[関係者を登録する](upgrade-enlist-stakeholders.md) |
|**2** |**プロジェクトビジョンの定義** |ビジョンとは、"全体像" または最終的な状態のことで、"このプロジェクトを実行しているのはなぜですか?" という質問に答えることができます。 理想的なビジョンは、組織のビジネスドライバーとユーザーの価値に対応します。視点を追加します。 |[プロジェクトビジョン](upgrade-define-project-scope.md#project-vision) |
|**3** |**プロジェクトの対象範囲を定義する** |ビジョンは、時間の経過と共に、さまざまなフェーズを通じて実現される場合があります。 プロジェクトのスコープは、現時点でのプロジェクトの焦点を定義しており、プロジェクトチームが現在のタスクに重点を置いているので、長期的なビジョンを実現できるようにします。 |[プロジェクトのスコープ](upgrade-define-project-scope.md#project-scope) |
|**4** |**プロジェクトの目標を定義する** |目標によって目的の結果が定義され、プロジェクトの成否を測定できるようになります。 目標は目標とキーの結果 (OKRs) として定義できます。また、プロジェクトの成功の測定は、成功の成否の指標 (KSIs) として定義できます。 お客様は、お客様が所有権を確実に把握し、これらの達成率を定義されたプロジェクトタスクに合わせることができるようにするために、プロジェクト関係者からすべての参加を得ることが重要です。 目標には、技術面とユーザーに重点を置いた成功の組み合わせが含まれている必要があります。 |[プロジェクトの目標](upgrade-define-project-scope.md#project-goals) |
|**5** |**リスクと軽減計画を特定する** |潜在的なリスクを事前に評価して、発生する可能性のある問題を解決するための緩和計画を定義することが重要です。これにより、プロジェクトは目標に近づけることができます。 リスク登録は、プロジェクトのリスクを追跡するための優れたツールであり、それがどのような可能性があるかと、リスクの可能性が高いと共に、軽減計画を捕捉します。 次の表は、サンプルのリスク登録を示しています。 |[リスクと軽減](upgrade-define-project-scope.md#risks-and-mitigation) |
|**6** |**タイムラインを定義する** |主要なマイルストーンのタイムラインを設定します (たとえば、すべてのユーザーについては Skype for Business を使用して Teams を有効にします)。また、完了日に加えて、ユーザーの段階的なアップグレードを開始します。 定義されたタイムラインは、プロジェクトチームが一貫した終了状態に向かうことを支援し、適切な作業バックスケジュールを通知して、プロジェクトが順調に進んでいることを確認します。(タスクがリストにある) タイムラインの速度が速すぎないことを検討してください。 |[時間](upgrade-define-project-scope.md#timeline)<br><br>[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit)|
|**7** |**適切な Skype for Business および Teams のアップグレードと共存戦略を定義する** |既存の Skype for Business ユーザーである場合、Teams への完全な移行には時間がかかることがあります。 ただし、今すぐ Teams を Skype for Business と共存する形で有効にすることによって、関係するユーザーが Teams の価値を実感し始められるようになります。 2 つのアプリの間で重複する機能があることから、利用可能な共存およびアップグレードモードを再確認すると、お客様の組織にとってどのパスが適しているかを判断するのに役立ちます。 最適なエクスペリエンスを実現するには、すべてのユーザーに展開する前に、計画した共存戦略を試験的に実行します。 |[Microsoft Teams と Skype for Business の共存と相互運用性について](teams-and-skypeforbusiness-coexistence-and-interoperability.md)<br><br>[アップグレードの行程を選択する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)|

### <a name="days-8ndash15-evaluate-your-organizations-readiness-for-teams"></a>日 8&ndash;日: チーム向けの組織の準備状況を評価する

|ステップ | |概要 |設備 |
|---|---|---|---|
|**1** |**リスクと要件を特定するために既存の環境を評価する** |環境を評価することで、全体的な展開に影響を与えるリスクと要件を特定することができます。 これらの項目を事前に特定することで、成功を確実にするために計画を調整することができます。 |[Teams にアップグレードする前に環境を評価する](upgrade-plan-journey-evaluate-environment.md) |
|**2** |**Office 365 および Teams のテクニカルオンボードを完了する** |既存のオンボードチェックリストを活用して、タスクやアクティビティを特定し、チームとの共同作業と音声機能のための技術的な準備を完了します。 |[Teams にアップグレードするためのサービスを準備する](upgrade-prepare-environment-prepare-service.md) |
|**3** |**チーム用にネットワークを最適化する (特にリアルタイムのメディアシナリオ)** |オーディオ、ビデオ、または会議を展開している場合は、その機能を利用できるようにネットワークを最適化するための追加の手順を実行することができます。 Teams では&mdash;、ほとんどのネットワーク条件下で&mdash;、適応してパフォーマンスを向上させることができるオーディオおよびビデオテクノロジ (コーデック) が使用されています。 最適かつ一貫性のあるパフォーマンスを確保するために、Teams 用にネットワークを準備する必要があります。 |[Teams にアップグレードするためにネットワークを準備する](upgrade-prepare-environment-prepare-network.md) |
|**4** |**組織的な変更の準備状況を評価する** |チームの価値を実現するには、ユーザーが実際にそれを使用する必要があります。 チームを有効にするだけでは、自分の目標を達成できるという保証はありません。 ユーザーにはさまざまなユースケースとさまざまな学習スタイルがあり、さまざまな速度で新しいテクノロジに対応しています。 ユーザーのベースを理解することで、ユーザーの導入を容易にするための適切なレベルの教育を準備することができます。 |[組織変更の準備](upgrade-org-change-readiness.md#organizational-change-readiness) |
|**5** |**ユーザーによる通信、トレーニング、およびサポートの方法を定義するためのユーザーの準備計画を準備する** |新しいテクノロジの receptiveness を最大限に活用するには、お客様が定義したペルソナと cohorts に合わせてカスタマイズされた、広範なリーチメッセージング (ビジョン/バリューメッセージングとユニバーサルユースケース) とメッセージング、トレーニング、サポートを組み合わせて使います。必要に応じて、laggards にもご利用ください。 このカスタマイズされたプランは、ユーザーがより迅速にチームに関連することを可能にし、ニーズを理解していることを示すことで、ユーザーの導入を容易にします。 これは、パイロット、オンボード、チームへのアップグレードの際に使用できます。 |[ユーザーの研修計画を準備する](upgrade-user-readiness.md)<br><br>[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit)<br><br>[Teams ビデオトレーニング](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?wt.mc_id=otc_home)<br><br>[Skype for Business から Teams に切り替える](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964) |
|**6** |**Microsoft Teams の保留中のリリースをアナウンスする** |ユーザーとコミュニケーションを取ることで、ユーザーの気持ちを感じることができます。混乱を招き、Microsoft Teams についての魅力を招き、Skype for Business からのアップグレードを迅速に行うことができます。 | [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
|**7** |**チームの IT スタッフを準備する** |Office 365 テナント管理者、テクニカルリーダー、およびサポートデスクは、高品質なユーザーエクスペリエンスを提供する責任を負うものとします。 これには、チームをサポートし、ユーザーに対してチームを構成する準備ができていること、発生する可能性のある問題のトラブルシューティングと解決が効果的であることを確認することが含まれます。 |[Microsoft Teams の IT スタッフを準備する](https://docs.microsoft.com/microsoftteams/upgrade-prepare-it-pros)<br><br>[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |

### <a name="days-16ndash60-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>15&ndash;日 60: パイロットを実行して、組織の準備ができていることを確認し、チームに最適な旅を通知します。

|ステップ | |概要 |設備 |
|---|---|---|---|
|**1** |**パイロット物流の概要** |試験的な開始日と終了日が定義され、成功を測定するための明確に定義された目標。 これらの目標は、より幅広いプロジェクトの範囲に合わせる必要があります。パイロットが終了した後に、パスを前方に通知するために使用されます。 |[パイロット物流の概要](pilot-essentials.md#1-outline-pilot-logistics) |
|**2** |**パイロット参加者とテストシナリオを選択する** |ロールやペルソナに基づかず、プロジェクトやチーム間の作業に基づいて、試験的な参加者を選択します。 パイロットは、IT、トレーニング、ヘルプデスクの主要な人物に延長する必要があるため、ソリューションを完全に最適化しながら、プロジェクト管理リソースを完全に最適化して、トップの Skype for Business ユーザーを含めるようにします。 |[パイロット参加者とテストシナリオを選択する](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
|**3** |**テスト計画とフィードバックアンケートを設計する** |参加者が完了するための明確に定義されたタスクと、それらのユーザーがフィードバックを共有するための方法を特定します。 タスクをグループ化して、現実世界のシナリオをユーザーに提供し、日常業務の関連性を実証します。 |[テスト計画とフィードバックアンケートを設計する](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
|**4** |**パイロットのコミュニケーション計画を作成する** |何が起こっているか、いつ、なぜ、何が起こるのかについて、パイロットの参加者を教育します。 参加と最大の参加を促進するには、ユーザー値のメッセージング機能と、ユーザーがパイロットの進行に応じて追加情報を取得できるようにするためのトレーニングとサポートへのリンクを含める必要があります。 |[コミュニケーション計画を作成する](pilot-essentials.md#4-create-your-communications-plan)<br><br>[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
|**5** |**パイロットの実施** |パイロットの実施には、ユーザーとの通信、ネットワークと使用状況の監視、ネットワークのパフォーマンスと通話品質の維持、参加者からのフィードバックの収集、関連する質問のヘルプデスクチケットの確認などが含まれます。Iis. |[パイロットの実施](pilot-essentials.md#5-conduct-your-pilot) |
|**6** |**高い知識の評価と、繰越計画の評価** |すべてのフィードバックアンケート、最終的なネットワーク統計情報、および目標に対する分析のサポートチケットを収集して、計画を実装するかどうかを決定します。 |[高い知識の評価と、繰越計画の評価](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan) |

### <a name="day-60-until-upgrade-deploy-teams-in-coexistence-with-skype-for-business"></a>アップグレードまでの日数 60: Skype for Business との共存にチームを展開する

|ステップ | |概要 |設備 |
|---|---|---|---|
|**1** |**Teams の公式リリースを発表する** |チームの組織の立ち上げを開始することについて、ユーザーに連絡して、理解と土地の価値とユーザーの利益を確保します。 起動イベントやメールなど、複数の形式で通信することを検討してください。 |[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
|**2** |**ユーザーに適切な共存モードを有効にする** |組織に適した [共存] モードを設定するには、次の手順を実行します。 |[共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md) |
|**3** |**チームロードマップについて常に情報を受け取る** |Teams のロードマップを監視し、組織の準備状況を継続的に評価して、組織が Teams に移行するための適切な時間を特定します。 |[Teams のロードマップ](https://aka.ms/teamsroadmap) |
|**4** |**追加の通信を送信し、** チームのエキスパートと協力して、チームの興奮と導入を推進する |継続的なコミュニケーションとチャンピオンを利用して、チームの魅力をお勧めします。 |[Microsoft 365 のチャンピオンプログラム](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>Upgrade

**チームに正式な移行を行います。** ユーザーをアップグレードする場合は、ユーザーを [**チームのみ**] の [共存] モードに移動します。 Teams は、チャット、会議、通話、共同作業のためのプライマリアプリとなり、Skype for Business アプリへのアクセスが無効になります。 このフェーズの技術的な側面は非常に単純ですが、変更によってユーザーエクスペリエンスがどのような影響を受ける可能性があるかを考慮し、ユーザーが自分のアクティビティを Skype for Business からチームに正式に移行できるようにすることを検討してください。 クライアントごとに異なるエクスペリエンスを実現するには、[エンドツーエンドのアップグレード] ウィンドウを45日間に制限してみてください。

### <a name="days-1ndash45-implement-your-upgrade-from-skype-for-business-to-teams"></a>日 1&ndash;45: Skype for Business から Teams へのアップグレードの実装

|ステップ | |概要 |設備 |
|---|---|---|---|
|**1** |**前に説明したアップグレード前のアクティビティを完了したことを確認する** |すべての計画および準備アクティビティの完了を確認して、アップグレードが成功したことを確認します。 |上記すべて |
|**2** |**最初のアップグレードグループのユーザーとの通信を開始する** |アップグレード前とアップグレード後の通信プランの実行を開始して、認知度を向上させることができます。これには、アップグレードの前に、チームのメリットをユーザーに伝えてください。 |[ユーザーの研修計画を準備する](upgrade-user-readiness.md)<br><br>[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit)<br><br>[Teams ビデオトレーニング](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?wt.mc_id=otc_home)<br><br>[Skype for Business から Teams に切り替える](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964) |
|**3** |**最初のアップグレードグループのユーザーに対してのみ、共存モードをチームに有効にする** |Skype for Business 環境に適した手順に従って、ユーザーの技術的な移行を実行します。 |[Skype for Business Online から Teams にアップグレードする](upgrade-to-teams-execute-skypeforbusinessonline.md)<br><br>[Skype for Business ハイブリッド展開から Teams にアップグレードする](upgrade-to-teams-execute-skypeforbusinesshybrid.md)<br><br>[Skype for Business オンプレミスの展開から Teams にアップグレードする](upgrade-to-teams-execute-skypeforbusinessonpremises.md) |
|**4** |**ローリングサイクルで残りのアップグレードグループについて、上記のアップグレードアクティビティを繰り返す** |引き続き継続的な通信計画を推進し、プランに基づいてユーザーグループをアップグレードします。 | |
|**5** |**アップグレード後のフィードバックアンケートをすべてのユーザーに送信する** |フィードバックアンケートを活用して、ユーザーからフィードバックや洞察を得ることができます。 |[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>アップグレード後

**Teams でビジネス価値を最大限に活用する。** 組織が Teams に完全にアップグレードされた後は、目標に対する成功を評価し、勢いを前進させる計画を実装します。

### <a name="days-1ndash14-measure-the-success-of-your-upgrade"></a>日 1&ndash;: アップグレードの成否を評価する

|ステップ | |概要 |設備 |
|---|---|---|---|
|**1** |**最初のアップグレード成功の評価** |アップグレード前のフェーズで確立した目標に対する進捗状況を評価します。 |[プロジェクトの目標](upgrade-define-project-scope.md#project-goals) |
|**2** |**トラッキングされない目標に対するリスク軽減計画を実装します。** |達成していない目標に対して、軽減またはコース修正の戦略を定義します。 |[プロジェクトの目標](upgrade-define-project-scope.md#project-goals) |

### <a name="ongoing"></a>現状

|ステップ | |概要 |設備 |
|---|---|---|---|
|**1** |**ネットワークの健全性と品質の監視** |ネットワークの健全性を監視して問題を緩和するための計画を実施することにより、有益なユーザー エクスペリエンスが確実に得られるようになるとともに、サポート デスクへの問い合わせを削減することにつながります。 |[ネットワークの健全性と品質の監視](continue-journey.md#monitor-for-network-health-and-quality) |
|**2** |**ユーザーの機運と導入を促進する** |継続的な導入計画を使用して、ユーザーの採用を促し、チームの興奮を維持します。 |[ユーザーの機運と導入を促進する](continue-journey.md#drive-user-momentum-and-adoption) |
|**3** |**新しい機能に対して準備する** |組織内で変更サイクルを確立することにより、継続的なコラボレーションの改善を管理したり、最大の価値を実現したりするための準備が確実に整います。 |[新しい機能に対して準備する](continue-journey.md#prepare-for-new-functionality) |

> [!Note]
> Skype のアップグレードに関するコンテンツは、継続的に進化しています。 最新のガイダンスを確認して、 [Teams のブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)を参照してください。

> [!Important]
> Skype for Business Online は、2021年7月31日に廃止されます。その後、アクセスまたはサポートされなくなります。 給付金を最大限に活用し、組織がアップグレードを実装するための適切な時間を確保するために、Microsoft Teams の現在の旅を開始することをお勧めします。 アップグレードが正常に完了した場合は、技術的かつユーザーの準備ができていることに注意してください。このガイドは、Microsoft Teams への旅に進むときに必ずご利用ください。
