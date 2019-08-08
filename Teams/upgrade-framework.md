---
title: アップグレードのフレームワークについて
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: 確実な実績のあるフレームワークを使用して、Skype for Business から Teams に組織のアップグレードの過程をサポートする
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52564961f3737b3b5ed9c48686adab1fe040b44d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236411"
---
# <a name="about-the-upgrade-framework"></a>アップグレードのフレームワークについて

アップグレードの過程から推量を行うため、microsoft は、変更を実装するための実証済みのフレームワークを採用しました。 次に示すように、フレームワークの各手順は前の手順で構築されており、最適な結果を得るためには、次の手順に従うことをお勧めします。  

まず、適切なステークホルダーを集めて、アップグレード計画を定義します (例: スコープ、目標、タイムライン)。 計画を立て、テクニカル環境とエンドユーザーが Teams を使用できるようになったことを確認します。 次に、準備が整った段階で、パイロットから組織全体のアップグレードに移行します。 組織がチームに参加したら、品質を監視し、ユーザーの導入を加速する運用計画を確立します。

![アップグレード過程フレームワークの図](media/upgrade-banner-main.png "プロジェクトが適切なプロジェクトチームで成功のために設定されていることを確認します。プロジェクトのスコープ、目標、タイムラインを定義します。テクニカルとユーザーの両方の準備ができていることを確認します。ロールアウト計画を実行します。最高の結果を得るには、勢いを維持します。")

アップグレードプロセスの場所を特定するには、関連ページでこのフレームワークのグラフィックを探します。

## <a name="sample-upgrade-timeline"></a>アップグレードタイムラインの例

変更の計画を開始すると、アップグレードの過程が開始されます。 このガイドラインとして成功フレームワークを利用することによって、アップグレードの計画と準備を行うための段階的なタイムラインの例として、アップグレードを通じてアップグレードを行う方法と、アップグレード後の運用フェーズとの間の維持と増幅の設計を行うことができます。結果。 

> [!NOTE]
> チームへの旅には、複数の [モード](https://aka.ms/skypetoteams-coexist) の活用、さまざまなタイミングでのユーザーのグループのアップグレードが含まれていることがわかっています。これにより、チームとの勢いを維持しながら、ユーザーのアップグレードエクスペリエンスを制御することができます。  

アップグレード過程がどのように展開されるかを示すために、次のサンプル計画を用意しています。これにより、Skype for Business Online から部門間のモードへの移動が定義されています。 さらに、サンプルの計画では、ユーザーを4つのアップグレードグループまたは cohorts に分類した組織の概要を示します。 これをテンプレートとして使用して、チームへの具体的な旅をカバーし、使用しているさまざまな [モード](https://aka.ms/skypetoteams-coexist) とユーザーのセグメント化を行うアップグレードグループの数を組み込み、プランをカスタマイズします。 

## <a name="pre-upgrade"></a>アップグレード前

**チームの組織を準備**します。 チームへのアップグレードを成功させるためには、準備のために十分な時間を割り当てることが重要です。 組織が Teams の価値をすぐに実感できるだけでなく、チームの準備が整うとすぐに Skype for Business からアップグレードを迅速に開始できるようになります。 Skype for Business と共にチームを既に有効にしている場合は、これらのアップグレード前のアクティビティをチェックポイントとして使用して、ユーザーをチームにアップグレードする前に、組織の準備ができていることを確認します。 

> [!TIP]
> サンプルアップグレードプロジェクト計画とパイロットテスト計画に加えて、コミュニケーションやユーザーアンケートなどのテンプレートのユーザー準備資料の [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) をダウンロードします。 このキットで利用できるアイテムには、以下のリストでアスタリスク (*) が付いています。

### <a name="plan-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>計画: 組織が長期間の成功を確実に設定できるようにアップグレード計画を作成する

| ステップ |  | 概要 | 設備 |
|------|--|---------|----------|
| **1** | **関係者を定義する** | アップグレードの成功のために責任を負うプロジェクトチームメンバーを割り当てます。 | [関係者を登録する](upgrade-enlist-stakeholders.md) |
| **2** | **プロジェクトのビジョンとスコープを定義する** | "全体像" ビジョンと現在のプロジェクトスコープを設計して、アップグレードに向けた青写真を作成します。 | [プロジェクトビジョン](upgrade-define-project-scope.md#project-vision) <br> <br>[プロジェクトのスコープ](upgrade-define-project-scope.md#project-scope) |
| **3** | **プロジェクトの目標を定義する** | 進捗状況とプロジェクトの成功率の測定を可能にするターゲット目標を設定します。 | [プロジェクトの目標](upgrade-define-project-scope.md#project-goals) |
| **4** | **リスクと軽減計画を特定する** | リスク軽減計画を確立して、プロジェクトをすぐに把握できるようにします。 | [リスクと軽減](upgrade-define-project-scope.md#risks-and-mitigation) |
| **5** | **タイムラインを定義する** | タイムラインと主要なマイルストーンを設定して、プロジェクトを予算内に維持することができます。 | [時間](upgrade-define-project-scope.md#timeline) <br><br> [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **6** | **適切な Skype for Business および Teams のアップグレードと共存戦略を定義する** | Skype for Business から組織のチームへの最適なパスを確保するために、自分の旅を地図にします。 | [Microsoft Teams と Skype for Business の共存と相互運用性について](teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br><br> [アップグレードの行程を選択する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) |


### <a name="prepare-evaluate-your-organizations-readiness-for-teams"></a>準備: Teams に対する組織の準備を評価する

| ステップ |  | 概要 | 設備 |
|------|--|---------|----------|
| **1** | **環境を評価して、チームのテクニカルオンボードを完成させる** | 環境のユーザーエクスペリエンスを最適化し、時間の経過と共にアップグレードを容易にするために、チームでの準備が整っていることを確認します。 | [Teams にアップグレードする前に、環境を評価して](upgrade-plan-journey-evaluate-environment.md)ください。<br><br> [Teams にアップグレードするためのサービスを準備する](upgrade-prepare-environment-prepare-service.md) |
| **2** | **チーム用にネットワークを最適化する (特にリアルタイムのメディアシナリオ)** | オーディオ、ビデオ、または会議を展開している場合は、その機能を利用できるようにネットワークを最適化するために、次の追加の手順を実行します。 | [Teams にアップグレードするためにネットワークを準備する](upgrade-prepare-environment-prepare-network.md) |
| **3** | **組織の変更の準備を評価し、チームワークのシナリオを定義する** | ユーザのベースを理解して、適切な価値のあるメッセージと教育レベルを準備し、ユーザーの導入を容易にします。 | [組織変更の準備](upgrade-org-change-readiness.md#organizational-change-readiness) |
| **4** | **ユーザーによる通信、トレーニング、およびサポートの方法を定義するためのユーザーの準備計画を準備する** | コミュニケーション、トレーニング、サポート計画をカスタマイズして、新しいテクノロジに最適な receptiveness を実現します。 | [ユーザーの研修計画を準備する](upgrade-user-readiness.md)<br><br>[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **5** | **Microsoft Teams の保留中のリリースをアナウンスする** | 早期にコミュニケーションして、ユーザーの気持ちを抑え、混乱を減らし、興奮を生み出します。 | [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **6** | **チームの IT スタッフを準備する** | テクニカルおよびサポート担当者が、チームの技術環境をサポートするために必要なすべての機能を備えていることを確認します。 | [Microsoft Teams の IT スタッフを準備する](upgrade-prepare-it-pros.md) <br><br> [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |

### <a name="pilot-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>パイロット: パイロットを実行して、組織の準備ができていることを確認し、チームに最適な旅を通知します。

| ステップ |  | 概要 | 設備 |
|------|--|---------|----------|
| **1** | **パイロット物流の概要** | 組織がアップグレードまたは共存する準備ができているかどうかを検証するための、正式なパイロット物流を定義します。 | [パイロット物流の概要](pilot-essentials.md#1-outline-pilot-logistics) |
| **2** | **パイロット参加者とテストシナリオを選択する** | チームワークシナリオを検証し、チームの準備を確認できるユーザーを特定します。 | [パイロット参加者とテストシナリオを選択する](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
| **3** | **テスト計画とフィードバックアンケートを設計する** | 参加者が完了するための明確に定義されたタスクと、それらのユーザーがフィードバックを共有するための方法を特定します。 | [テスト計画とフィードバックアンケートを設計する](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
| **4** | **パイロットのコミュニケーション計画を作成する** | 何が起こっているか、いつ、なぜ、何が起こるのかについて、パイロットの参加者を教育します。 | [コミュニケーション計画を作成する](pilot-essentials.md#4-create-your-communications-plan)<br><br>[アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **5** | **パイロットの実施** | パイロットを開始し、進捗状況を追跡し、必要に応じて反復処理を行い、パイロットの結果を最適化します。 | [パイロットの実施](pilot-essentials.md#5-conduct-your-pilot) |
| **6** | **高い知識の評価と、繰越計画の評価** | ユーザーからのフィードバック、ネットワークの統計情報、サポートチケットを収集して目標を分析し、繰越計画を決定します。 | [高い知識の評価と、繰越計画の評価](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan)

### <a name="deploy-run-teams-in-coexistence-with-skype-for-business"></a>展開: Skype for Business との共存で Teams を実行する

| ステップ |  | 概要 | 設備 |
|------|--|---------|----------|
| **1** | **Teams の公式リリースを発表する** | Teams の準備ができたときに、正式な立ち上げのお知らせを送信して、興奮と勢いを生み出します。 | [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **2** | **ユーザーに適切な共存モードを有効にする** | 組織に適した [共存] モードを設定するには、次の手順を実行します。 | [共存およびアップグレードを設定する](setting-your-coexistence-and-upgrade-settings.md) |
| **3** | **チームロードマップについて常に情報を受け取る** | チームロードマップを監視して、組織が Teams に移行するための適切な時間を特定します。 | [Teams のロードマップ](https://aka.ms/teamsroadmap) |
| **4** | **追加の通信を送信し、チームのエキスパートと協力して、チームの興奮と導入を推進する** | 継続的なコミュニケーションとチャンピオンを利用して、チームの魅力をお勧めします。 | [Microsoft 365 のチャンピオンプログラム](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>Upgrade 

**チームに正式な移行を行い**ます。 ユーザーをアップグレードする場合は、ユーザーをチーム専用モードに移動します。 Teams は、チャット、会議、通話、共同作業のためのプライマリアプリとなり、Skype for Business アプリへのアクセスが無効になります。 このフェーズの技術的な側面は非常に単純ですが、変更によってユーザーエクスペリエンスがどのような影響を受ける可能性があるかを考慮し、ユーザーが自分のアクティビティを Skype for Business からチームに正式に移行できるようにすることを検討してください。 クライアントごとに異なるエクスペリエンスを実現するには、[エンドツーエンドのアップグレード] ウィンドウを45日間に制限してみてください。

### <a name="upgrade-implement-your-upgrade-from-skype-for-business-to-teams"></a>アップグレード: Skype for Business から Teams へのアップグレードの実装

| ステップ |  | 概要 | 設備 |
|------|--|---------|----------|
| **1** | **上記で説明したアップグレード前のアクティビティを完了したことを確認します。** | すべての計画および準備アクティビティの完了を確認して、アップグレードの成功を確認します。 | 上記すべて |
| **2** | **最初のアップグレードグループのユーザーとの通信を開始する** | アップグレードが開始されたことをユーザーに通知し、プロセス全体を通じて通知された状態を維持します。 | [ユーザーの研修計画を準備する](upgrade-user-readiness.md) <br><br> [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |
| **3** | **最初のアップグレードグループのユーザーに対してのみ、共存モードをチームに有効にする** | Skype for Business 環境に適した手順に従って、ユーザーの技術的な移行を実行します。 | [Skype for Business Online から Teams にアップグレードする](upgrade-to-Teams-execute-SkypeforBusinessOnline.md) <br><br>[Skype for Business のハイブリッド環境またはオンプレミス環境から Teams にアップグレードする](upgrade-to-Teams-execute-SkypeforBusinessHybridOnprem.md)
| **4** | **ローリングサイクルで残りのアップグレードグループについて、上記のアップグレードアクティビティを繰り返す** | 引き続き継続的な通信計画を推進し、プランに基づいてユーザーグループをアップグレードします。 | |
| **5** | **アップグレード後のフィードバックアンケートをすべてのユーザーに送信する** | フィードバックアンケートを使用して、ユーザーからフィードバックや洞察を得ることができます。 | [アップグレード成功キット](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>アップグレード後

**Teams でビジネス価値を最大限に活用**する。 組織が Teams に完全にアップグレードされた後は、目標に対する成功を評価し、勢いを前進させる計画を実装します。 

### <a name="operate-measure-the-success-of-your-upgrade"></a>動作: アップグレードの成否を評価する

| ステップ |  | 概要 | 設備 |
|------|--|---------|----------|
| **1** | **最初のアップグレード成功の評価** | アップグレード前のフェーズで確立した目標に対する進捗状況を評価します。 | [プロジェクトの目標](upgrade-define-project-scope.md#project-goals) |
| **2** | **トラッキングされていない目標に対するリスク軽減計画を実装する** | 達成していない目標に対して、軽減またはコース修正の戦略を定義します。 | [プロジェクトの目標](upgrade-define-project-scope.md#project-goals) |
| **3** | **ネットワークの健全性と品質の監視** | 良好なユーザーエクスペリエンスを確保し、サポートデスクへの通話を減らすための品質チェックと監視の計画を実装します。 | [ネットワークの健全性と品質の監視](continue-journey.md#monitor-for-network-health-and-quality) |
| **4** | **ユーザーの機運と導入を促進する** | 継続的な導入計画を使用して、ユーザーの採用を促し、チームの興奮を維持します。 | [ユーザーの機運と導入を促進する](continue-journey.md#drive-user-momentum-and-adoption) |
| **5** | **新しい機能に対して準備する** | 新しい革新と製品の改善のために変更サイクルを確立して、最大の価値を実感してください。 | [新しい機能に対して準備する](continue-journey.md#prepare-for-new-functionality)


> [!Note]
> アップグレードに関するコンテンツは、継続的に進化し続けています。 最新のガイダンスを確認して、 [Teams のブログ](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)を参照してください。 

> [!Important]
> Skype for Business Online は、2021年7月31日に廃止されます。その後、アクセスまたはサポートされなくなります。 給付金を最大限に活用し、組織がアップグレードを実装するための適切な時間を確保するために、Microsoft Teams の現在の旅を開始することをお勧めします。 アップグレードが正常に完了した場合は、技術的かつユーザーの準備ができていることに注意してください。このガイドは、Microsoft Teams への旅に進むときに必ずご利用ください。
