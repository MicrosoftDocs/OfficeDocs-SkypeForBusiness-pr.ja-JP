---
title: Skype for Business から Microsoft Teams へのアップグレード| モード、共存
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen, bjwhalen
description: Skype for Business と Microsoft Teams の共存オプションおよびモードの詳細と、いくつかのシナリオ例での Skype for Business から Teams へのアップグレード手順。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7509d0f3d6e3e557f6b7ccd388f7b9b340705bba
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236169"
---
![展開と実装を強調したアップグレードの図](media/upgrade-banner-deployment.png "展開と実装のステージに重点を置いたアップグレードの段階")

この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。 先に進む前に、次のアクティビティを完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Skype for Business から Teams へのアップグレード手順を選択する

既存の Skype for Business ユーザーである場合、Teams への完全な移行には時間がかかることがあります。 ただし、今すぐ Teams を Skype for Business と共存する形で有効にすることによって、関係するユーザーが Teams の価値を実感し始められるようになります。 2 つのアプリの間で重複する機能があることから、利用可能な共存およびアップグレードモードを再確認すると、お客様の組織にとってどのパスが適しているかを判断するのに役立ちます。 たとえば、すべてのワークロードを、相互運用性のない状態で、両方のソリューションで有効にすることを選ぶことが考えられます。 または、お客様の組織において、すべてのユーザーを Teams にアップグレードさせられる準備が整うまで、段階的に Teams の機能を導入したり、一部の機能を使用できるユーザーのグループを絞り込んだりして、ユーザー エクスペリエンスを管理することを決めることも考えられます。 組織のために適切なアップグレード手順を評価するために、パイロットの結果を使用します。

> [!IMPORTANT]
> Skype for Business Online は、2021年7月31日に廃止されます。その後、アクセスまたはサポートされなくなります。 給付金を最大限に活用し、組織がアップグレードを実装するための適切な時間を確保するために、Microsoft Teams の現在の旅を開始することをお勧めします。

この記事では、Skype for Business および Teams のどのモダリティをユーザーが利用できるようにするかを管理できるようになる、さまざまなモードの概要を示します。 どのような展開においても、お客様の組織で Teams へのアップグレードを行う前に、選択したユーザー グループで、[対象の計画をパイロットする](pilot-essentials.md)ことを強くお勧めします。 新しいテクノロジーを導入することは、ユーザーにとって混乱をきたす可能性があるものであることを忘れないでください。 ここで概説されているいずれかのモードを実施する前に、ユーザーの準備状況を評価して、コミュニケーションおよびトレーニングの計画を実行するために時間を割きます。

> [!TIP]
> お客様は、指導、ベストプラクティス、およびアップグレードを開始するために設計されたリソースを共有するライブのインタラクティブなワークショップをお申し込みください。
>
>最初に[アップグレード](https://aka.ms/SkypeToTeamsPlanning)セッションの計画に参加してください。


## <a name="upgrade-journey-building-blocks"></a>アップグレード手順の構成単位

お客様の組織を Teams に移行するために正式に準備するためには、最終的に組織が Teams を唯一のコミュニケーションとコラボレーションのソリューションとして完全に受け入れられるようになるアップグレード シナリオ計画を開始する必要があります。

Skype for Business から Teams へのアップグレードに関連した、さまざまなモードや、コンセプトや、用語についての知識を深めることは、意思決定プロセスのガイドとして役に立ちます。 詳細については、「[Microsoft Teams と Skype for Business の共存および相互運用性について理解する](https://aka.ms/SkypeToTeams-Coexist)」をご覧ください。

日常のコミュニケーションおよびコラボレーションの必要性に応じて、一部のユーザーが Teams のみを使用する準備が整っている場合、**Teams Only** モードを有効にすることによって、それらのユーザーの Teams へのアップグレードを開始することができます。

組織全体でTeams に移行することが考えられない場合は、**アイランド**共存モードで Skype for Business を残した状態で Teams のパイロット使用を開始することができます。 追加の共存モード (**Skype for Business と Teams でのコラボレーション**および**Skype for Business と Teams でのコラボレーションおよび会議**) が今後数か月間で徐々に完全に利用できるようになるとともに、Skype for Business をお客さまの組織での統一されたコミュニケーション ソリューションとして維持しながら、Teams をグループ コラボレーションのソリューションとして完全に導入し始めることもできます。 これは、Skype for Business Server (オンプレミスまたはハイブリッド) を使用しているユーザーや、Teams に向かう中で共存での使用期間が長くなるような極めて複雑な状況にあるユーザーに対して、マイクロソフトが推奨するパスです。

![Skype For business から Teams へのアップグレード文書パーツのスクリーンショット]Skype for (media/upgrade_journeys_building_block.png "business から teams へのアップグレード文書パーツのスクリーンショット。チームのコラボレーション&ndash;のみモードで、チームのコラボレーションと会議モード、孤島モード、チーム専用モード、skype for business で構成される skype for business で構成されています。ビジネス&ndash;専用モード。")

次の表で、共存モードとアップグレード モードを比較します。

|モード |状況 |推奨される使用状態 |利点 |注意事項 |
|---|---|---|---|---|
|アイランド |より小規模またはシンプルな Skype for Busness の展開<br><br>いくつかの短期的な複雑な状況を管理して、Teams により速やかに移行するための能力と意思。 |できるだけ早く完全な Teams エクスペリエンスに移動する<br><br>Teams の概念実証 (PoC) の実施<br><br>Skype for Business Online を導入した組織に対して推奨されるアップグレード パス |運用が簡単<br><br>すべての機能において傑出した、最も豊かな Teams エクスエぺリエンス |混乱を排除し、Teams の使用を推進するためには、良好なユーザー コミュニケーションが必須<br><br>出口戦略において、Teams Only フェーズへのアップグレードを開始する前にユーザーが完全に Teams を導入することが必須<br><br>アイランド モードのユーザーに対する相互運用性はなし。また、ユーザーの Skype for Business アカウントがオンプレミスで所属している場合は Teams からのフェデレーションもなし|
|Skype for Business と Teams でのコラボレーション |Skype for Business の展開で、Teams ではまだ満たされていない要件がある (たとえば、先進的なコンプライアンスなど)<br><br>Skype for Business に対する長期的な必要性や、コミットメント|グループでの共同作業について最初に焦点をあてながら、Teams の導入を速やかに開始する<br><br>Skype for Business 上で、すべての統合コミュニケーション ワークロードを維持する<br><br>オンプレミス (またはハイブリッド) の Skype for Business からの移行を開始する組織の開始点としての使用を推奨|Teams と Skype for Business との間に重複する機能なし	<br><br>インスタント メッセージング チャットおよび会議のスケジュールが (通話に結びついている) Skype for Business に存在する<br><br>Teams Only のユーザーとの相互運用性|
|Skype for Business と Teams でのコラボレーションおよび会議 |エンタープライズ VoIP を頻繁に使用し、Teams 通話では適合しない要件がある Skype for Business の展開<br><br>Skype for Business に対する長期的な必要性や、コミットメント<br><br>サードパーティの会議サービスを使用する可能性|グループでの共同作業にとどまらず、Teams の導入を速やかに開始<br><br>ユーザーの会議のエクスペリエンスを改善<br><br>(一般的にエンタープライズ VoIP オンプレミスのために) 完全にアップグレードする準備が整う前に、Teams 会議を十分に活用することを望んでいる、オンプレミスの組織に対して推奨される使用 |重複する機能なし<br><br>Teams でのより優れた会議。 機能のロードマップ、UX とクロス プラットフォーム、品質と信頼性<br><br>Skype for Business と Teams との間での「より良い連携作業」エクスペリエンス<br><br>Teams Only の相互運用性ユーザー。|インスタント メッセージング およびチャットが (通話に結びついている) Skype for Business に存在する|
|Teams Only |[チームのみ] は、すべてのユーザーの最終的な保存先です。<br><br>Skype for Business の使用を継続する必要がある一部のユーザー<br><br>Skype for Business Online ユーザーを Teams にアップグレートしている一方で、Skype for Business オンプレミス ユーザーは Skype for Business Server 上にとどめている<br><br>展開済みのユーザーを既にアイランド モードにしており、ユーザーのグループでの Skype for Business の使用を廃止する準備が整っている |Skype for Business のさまざまな費用 (オンプレミス サーバーの運用、外注契約など) の削減<br><br>できるだけ早く、少なくとも一部のユーザーにおいて、完全な Teams エクスペリエンスに移行する|Skype for Business のみ、Skype for Business と Teams でのコラボレーション、Skype for Business と Teams でのコラボレーション、Skype for Business と Teams でのコラボレーションおよび会議において、ユーザーとの相互運用性で機能するクライアントを 1 つのみ提供して、ユーザーの混乱を抑制する|相互運用性のサポート範囲は、Skype for Business と Teams との間での基本的なチャットと通話、およびデスクトップ共有や複数パーティでのチャットおよび通話のための相互運用性のエスカレーション シナリオに限られる|
|Skype for Business のみ |Skype for Business の使用を継続する必要がある一部のユーザー<br><br>|ユーザーとの相互運用性で機能するクライアントを 1 つのみ提供して、ユーザーの混乱を抑制する<br><br>ユーザーは招待された場合に Teams 会議に参加することができる|現時点で Skype for Business によってのみ適合しているビジネス要件に適合する<br><br>Teams Only のユーザーとの相互運用性|相互運用性のサポート範囲は、Skype for Business と Teams との間での基本的なチャットと通話、およびデスクトップ共有や複数パーティでのチャットおよび通話のための相互運用性のエスカレーション シナリオに限られる|

> [!TIP]
> Skype for Business がまだ使用されているときに、チームで有効にする機能に基づいて推奨されるアップグレードモードを特定するには、 [skype To Teams アップグレードウィザード](https://aka.ms/SkypeToTeamsWizard)をご利用ください。

## <a name="upgrade-journeys"></a>アップグレード手順

オンラインでもオンプレミスでも、Skype for Business から Teams へのアップグレードは、複数のアプローチで行うことができます。

- 直接的なアップグレード手順では、まず Skype for Business とともに Teams を評価および早期導入の一部として**アイランド** モードで展開し、組織内のすべてのユーザーの環境から Skype for Business を速やかに廃止するという目標とともに、お客様のユーザーを **Teams Only** モードにアップグレードします。 これは、Skype Business オンライン ユーザーに対して、それらのユーザーが同じアクション (チャット、通話、会議、スケジュール設定) を行うための 2 つのツールがあることで混乱しない限りにおいて、推奨される移行手順です。
- 段階的なアップグレード手順では、(*コーホート*とも呼ばれる) 特定のユーザー グループに対して、それらのユーザーのコミュニケーションおよびコラボレーションの要件に応じて、特定の共存およびアップグレード モードが提供されます。 時間の経過とともに、組織全体で Teams Only を使用する方向に収束していき、最終的には Skype for Business は置き換えられます。 ただし、お客様の組織で、たとえば基幹業務アプリケーションと統合する Unified Communications Managed API (UCMA) ベースのソリューションや、Skype for Business のみで利用可能な現在倫理的境界ソリューションや、**Teams Only** へのアップグレードに時間がかかる複雑なエンタープライズ VoIP 展開などに依存しているなどの、Skype for Business を保持するための差し迫ったビジネス上の理由がある場合は、部分的なユーザー集団のための 1 つの共存モードで Skype for Business ユーザーを保持しながら、一部のユーザーを **Teams Only** モードにアップグレードすることができます。 段階的なアップグレード手順は、Skype for Business と Teams でのコラボレーションの共存モードから開始して、Teams Only モードに移行するオンプレミス (およびハイブリッド) ユーザーに対して、それらのユーザーに対する要件が (Skype for Business と Teams でのコラボレーションおよび会議の共存モードを通して) 適合する場合において、推奨されるアプローチです。

> [!IMPORTANT]
> アップグレード手順の両方のタイプについて、お客様の組織で現在 Skype for Business オンプレミス展開のみを利用している場合、お客様のユーザーを **Teams Only** モードにアップグレードする前に、Skype for Business ハイブリッドの実装計画を開始する必要があります。 これにより、Teams との相互運用性の促進を図ることもできます。

> [!NOTE]
> **Teams Only** モードでは、コーホートの一部であるユーザーが Skype for Business Online に属していることを必要とします。また、Skype for Business と Teams との間の相互運用性を促進するために Skype for Business オンプレミス展開と Skype for Business Online テナントとの間のハイブリッド関係が必要となります。 Skype for Business Online への移行は、コーホートの一部であるユーザーのために、**Teams Only** モードにアップグレードする前に完了させる必要があります。 Skype for Business Server 2019、および CU8 アップデート適用済みの Skype for Business Server 2015 は、1 つの手順で Skype for Business Online への移行を管理してユーザーを **Teams Only** モードにアップグレードすることによって、オンプレミス ユーザーの Teams へのアップグレードの仕組みを簡素化することができます。

### <a name="direct-upgrade-journey"></a>直接的なアップグレード手順

直接的なアップグレード手順は次の図に示されています。

![アップグレード過程の直接のスクリーンショット](media/upgrade_journey_direct_upgrade.png "アップグレード過程の直接のスクリーンショット。すべてのユーザーは、最初はアイランドモードで Teams を使用してから、チーム専用モードに切り替えて、組織全体の終了状態が Teams にアップグレードされます。")

Teams は組織内のすべてのユーザーに展開され、**アイランド** モードで構成されます。 お客様の組織で Teams がすべてのコミュニケーションとコラボレーションのニーズを満たす準備が整ったら、ユーザーに通知して、**Teams Only** モードへのアップグレードを行います。 この時点で、Skype for Business は環境から廃止することができるようになります。

### <a name="gradual-upgrade-journey"></a>段階的なアップグレード手順

段階的なアップグレード手順の例は次の図に示されています。

![段階的なアップグレードの過程の例を示します]。(media/upgrade_journey_gradual_upgrade.png "段階的なアップグレードでは、cohorts ユーザーは最初に、評価のために孤島モードで Teams を使用し、その後、Skype For business を使用して早期に導入するためのさまざまなアップグレードモードでチームを使用しています。一部の cohorts はチーム専用モードに移行しますが、ユーザーの1つはチームのグループ作業と会議モードで Skype for Business を使用したままです。")

Teams は評価のために **アイランド** モードで組織内に展開されてから、それぞれのユーザー グループに対して異なる共存およびアップグレード モードに移行します。 たとえば、あるユーザーのグループでは**アイランド** モードが有効になり、別のグループでは **Skype for Business と Teams でのコラボレーションおよび会議**モードが有効になり、一方 3 番目のユーザー グループは **Skype for Business と Teams でのコラボレーションのみの**モードが有効になります。

時間の経過とともに、ユーザーのグループは **Teams Only** モードにアップグレードされます。その後に組織の残りの部分が続きます。 最終的に、組織全体で Skype for Business を廃止し、Teams のみをコミュニケーションとコラボレーションのために使用できる状態が整います。ビジネス要件によって Skype for Business が特定のグループのために保持される場合は、組織内のユーザーの大多数が Teams Only を使用することができます。 <br><br>
<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>判断ポイント</td><td><ul> どのアップグレード手順が組織のビジネス要件に適してますか?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>次のステップ</td><td><ul> お客様の組織での現在の展開モデル、ユース ケースのシナリオ、および主な考慮事項を特定することにより、組織に最も適した Teams への移行手順がわかるようになります。<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>判断ポイント</td><td><ul> お客様の組織に該当するアップグレード シナリオはどれですか?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次のステップ</td><td><ul> メッセージング、会議、および通話のビジネス要件に基づいて、お客様の組織のアップグレード手順のタイムラインを決定します。<br><br> アップグレード手順を完了するために必要な追加作業を決めます。<br><br></ul></td></tr>
</table>

組織にとって最高のアップグレード手順を選んだ後、[Teams に対するアップグレードを実行します](https://aka.ms/SkypeToTeams-Upgrade)。
