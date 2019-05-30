---
title: Microsoft Teams |アップグレード、孤島モード、相互運用ポリシー
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Skype for Business および Microsoft Teams の共存オプションと、Skype for Business と Teams の相互運用性について詳しく説明します。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06655b8c43bb912409b2a1c6a42d7509f45bf651
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548798"
---
![プロジェクト定義ステージに重点を置いたアップグレードの段階](media/upgrade-banner-project-definition.png "プロジェクト定義ステージに重点を置いたアップグレードの段階")

この記事は、アップグレードが行われるプロジェクト定義ステージの一部であり、スポンサー協力とプロジェクトチームを作成して、プロジェクトの範囲、目標、ビジョンを定義した後に行うアクティビティです。 先に進む前に、次のアクティビティを完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Microsoft Teams と Skype for Business の共存と相互運用性について

組織で Skype for Business を使用していて、Skype for Business と共に Teams の使用を開始しようとしている場合、またはチームへのアップグレードを開始しようとしている場合、2つのアプリケーションの共存方法、相互運用方法、およびその方法を理解することが重要です。Skype for Business から Teams への最終的なアップグレードに、ユーザーの移行を管理します。

> [!Tip]
> [共存および相互運用性の詳細については、こちらのセッション](https://aka.ms/teams-upgrade-coexistence-interop)をご覧ください。

## <a name="coexistence-of-teams-and-skype-for-business"></a>Teams と Skype for Business の共存

チームは、共同作業機能に加えて、チャット、通話、会議の機能を提供します。 チームの展開方法に応じて、これらの機能は、特定のユーザーに対して Skype for Business によって提供される機能と重複します。 既定のモードは、Skype for Business と共にチームを実行することです。ただし、これらの機能をユーザーに重複させないように設計された複数の共存モードのいずれかをユーザーに割り当てることができます。

どのパスが自分の組織に適しているかを判断するために、以下で説明する共存モードを確認することをお勧めします。

> [!Important]
> 新しいテクノロジを導入したり、既存の使い慣れた Skype for Business 環境に変更を加えたりすることで、新しいビジネス上のメリットを提供し、ユーザーの混乱を防ぐことができます。 この記事で説明されている変更を実装する前に、ユーザーの準備を評価し、コミュニケーションとトレーニングの計画を実装することが必要です。 さらに、組織全体に実装する前に、選択したユーザーのグループに計画を試験的に適用することを強くお勧めします。

### <a name="islands-mode"></a>諸島モード

既定では、ユーザーは Skype for Business と同時に、チャット、通話、会議などの類似した重複する機能を提供する2つの独立したソリューションとして Teams を実行できます。 チームユーザーは、チームやチャネルなどのコラボレーション機能、Office 365 のファイルへのアクセス、アプリケーションなどの機能を利用することもできます。

この共存モード (**孤島**) では、各クライアントアプリケーションは独立したアイランドとして動作します。 Skype for Business は、Skype for business とチームとのやり取りをします。 ユーザーは両方のクライアントを実行し、通信が開始されたクライアントでネイティブ通信を行うことができます。 このように、**孤島**モードでの相互運用性は不要です。

> [!Tip]
> Skype for Business Online のお客様に推奨されるパスは、既定の**アイランド**モードから開始して、組織内の導入の鮮やかさをドライブし、すぐに**Teams のみ**に移行することです。 オンプレミスおよびハイブリッドのお客様は、今後の**Skype For business**を、組織の共同作業モードではなく開始点として展開して、組織が採用できるようになった時点で**チーム**のグループ作業に進むことができます。Iis.

### <a name="skype-for-business-only"></a>Skype for Business のみ

この共存モードでは、ユーザーは、チャット、会議、通話の機能については Teams ではなく、Skype for Business にとどまります。また、チームとチャネルのチームは使用されません。 このモードは現在利用できます。ただし、現在の実装では、ユーザーのモダリティが自動的に無効になっていません。 この機能は今後ご利用になる予定です。 暫定的に、管理者は、Skype for Business を唯一の通信アプリケーションとして残しておく必要があるユーザーのために、Teams ライセンスを削除することができます。

### <a name="teams-only"></a>Teams Only

**Teams のみ**のユーザーは、Skype for business クライアントを使用して、既存の Skype for business 会議、またはアップグレードされていないユーザーまたは外部関係者によって開催された Skype for business の会議に参加できます。 アップグレードされたユーザーは、チームと Skype for Business の間の相互運用性機能を使用して、引き続き Skype for Business を使用している組織内の他のユーザーと通信することができます。ただし、アップグレードされたユーザーは、Skype for Business チャット、通話、会議を開始することはできません。

組織の一部またはすべてのユーザーが、唯一のコミュニケーションとコラボレーションツールとして Teams を使用する準備ができたら、そのユーザーを**チーム専用**モードにアップグレードできます。

チーム専用モードへの移行に関するその他の考慮事項については、「[チームのみモードの考慮事項](teams-only-mode-considerations.md)」を参照してください。

![Teams 確認メッセージのスクリーンショット](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "ユーザーがチーム専用ユーザーとしてアップグレードされた後に、特別モードで実行されている Skype For business クライアント")

### <a name="skype-for-business-with-teams-collaboration-this-mode-is-upcoming"></a>チームでの共同作業を行う Skype for Business (このモードは間もなく開催されます)

このモードを使用すると、引き続き Skype for Business で既存の投資を活用しながら、環境に Teams を導入することができます。 このモードでは、Skype for Business のチャット、通話、会議機能は変更されません。また、チームとチャネル、Office 365 内のファイルへのアクセスなど、チームのコラボレーション機能を追加することもできます。 社内またはハイブリッドの Skype for Business server の出発地点を持つ組織は、島々モードではなくこのモードを使用する必要があります。

### <a name="skype-for-business-with-teams-collaboration-and-meetings-this-mode-is-upcoming"></a>チームでの共同作業と会議を行った Skype for Business (このモードは間もなく開催されます)

この共存モードを使用すると、共同作業機能に加えて、組織内のチーム会議機能の可用性を向上させることができるため、お客様は、お客様は、お客様が、お客様が、お客様が、お客さまの翻訳などの新機能を活用できますブラウザーでの会議の翻訳とサポート。

このモードでのチームおよびチャネルベースの会話に Teams を使用すると、ユーザーはチームの使用を開始して、会議をスケジュールして実施します。 プライベートチャット、音声通話、ビデオ通話が Skype for Business に残ります。 この共存モードは、特に、エンタープライズ voip を利用している Skype for Business のオンプレミス展開のユーザーに適していますが、Teams へのアップグレードには時間がかかる場合がありますが、上位チーム会議を活用することをお勧めします。

> [!Note]
> 特定の共存モードで展開されると、チームと Skype for Business の[相互運用](#interoperability-of-teams-and-skype-for-business)が可能になり、ユーザーは互いにチャットしたり、通話を発信したり、組織内でチームへのアップグレード中に通信が流動的な状態に維持されるようになります。 共存モードは、相互運用性を制御します。 相互運用性を利用できるかどうかは、受信者の共存モードによって異なります。 たとえば、受信者がチャットを1つのクライアント (たとえば、Teams) でしか使用できないモードである場合は、通常、他のクライアント (この例では Skype for Business) を使用してチャットを開始したときに、チャットの相互運用性が利用可能になります。 一方、受信者が両方のクライアントでチャットが利用可能なモードになっている場合は、チャットのために相互運用性を利用することはできません。また、イニシエーターがチャットを開始した同じクライアントで、受信者がメッセージを受信します。

共存モード、前提条件、および管理の詳細については、「[チームと Skype For business を組み合わせて使用する組織向けの移行と相互運用性のガイダンス](https://aka.ms/SkypeToTeams-Interop)」および「[共存とアップグレードの設定](https://aka.ms/SkypeToTeams-SetCoexistence)」を参照してください。

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|判断ポイント|<ul><li>組織とユーザーのニーズに最も適合する共存モード</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|次の手順|<ul><li>アップグレードに最適な方法を選択します。</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Teams と Skype for Business の相互運用性

相互運用性とは、チームと Skype for Business ユーザーが同じ組織内でチームと skype for business の間で通信できる機能です。

### <a name="native-interop-and-interop-escalation"></a>ネイティブの相互運用性と相互運用エスカレーション

相互運用エクスペリエンスには、ネイティブと相互運用によるエスカレーションという2つの種類があります。

- ユーザーが現在使用しているクライアントで_ネイティブの相互運用_エクスペリエンスが発生します。 1人のユーザーは、Teams の Skype for Business クライアントに表示されます。 ネイティブの相互運用機能によって、他のクライアントに伝達されることはありません。ユーザーは、現在使用しているクライアントで会話を行うことができます。 ネイティブの相互運用エクスペリエンスは、1対1のチャットと通話です。
- _相互運用エスカレーション_の操作とは、ユーザーが高度な操作 (デスクトップの共有など) を実行するのに役立ちます。このサービスは、会議の作成を容易にして、その会議の操作を続けることができます。 会議は、アクションのイニシエーターのプラットフォームで作成されます。 このプラットフォームを使っていないユーザーが会議の参加を確認し、会議に参加します (クライアントの切り替え後)。

### <a name="native-interop-experiences"></a>ネイティブの相互運用エクスペリエンス

ユーザーに割り当てられている共存モード (前述のとおり) に応じて、次のネイティブの相互運用機能を使用できます。

- Skype for Business ユーザーは、チームユーザーと1対1のチャットを行うことができます。その逆も可能です。 相互運用機能のチャットは、Teams クラウドサービスの一部である相互運用ゲートウェイを通じて行う必要があります (そのため、オンラインである必要があります)。 相互運用機能のチャットはプレーンテキストです。リッチテキストと絵文字はサポートされていません。 チームのユーザーには、会話が相互運用スレッドであることが通知されます。Skype for Business ユーザーについても同様の通知が間もなく提供されます。

![Teams からの相互運用チャットエクスペリエンスのスクリーンショット](media/Interop_chat_experience_from_Teams.png "Teams からの相互運用チャット")

- Skype for Business ユーザーは、1対1の音声通話とビデオ通話を Teams ユーザーに対して行うことができます。また、その逆も可能です。

![Teams からの相互運用通話エクスペリエンスのスクリーンショット](media/Interop_calling_experience_from_Teams.png "Teams の相互運用通話のエクスペリエンス")

> [!Important]
> Skype for Business のオンプレミス展開での相互運用エクスペリエンスには、オンプレミス環境が Office 365 Skype for Business のハイブリッドモードになっている必要があります。 詳細については、「[移行と相互運用性のガイダンス](https://aka.ms/SkypeToTeams-Interop)」を参照してください。

これらの相互運用機能は、次のいずれかの共存モードが割り当てられているユーザーが利用できます。**チームコラボレーションを備えた skype For business**、**チームのコラボレーションと会議**、skype for business **ビジネスのみ**、または**チームのみ**。 孤島モードでは、ユーザーに対する相互運用性はありません。

### <a name="native-interop-experience-limitations"></a>ネイティブの相互運用機能のエクスペリエンスに関する制限事項

Teams と Skype for Business の間の相互運用チャットと相互運用通話の機能には、次のような機能がありません。

- マークダウン、rich text、および完全な絵文字セットは、Teams または Skype for Business ではサポートされていません。 チームチャットの作成ボックスのその他のネイティブ機能はサポートされていません。
- Teams と Skype for Business の間の画面共有 (デスクトップまたはアプリの共有) はサポートされません。
- Teams のグループチャット (複数パーティの会話) には、Teams を使用している参加者のみを含めることができます。
- Skype for Business の複数パーティの IM 会話 (グループチャット) には、Skype for Business を使用している参加者のみを含めることができます。
- 進行中のピアツーピアの音声通話またはビデオ通話を、Teams と Skype for Business の両方でサポートされていない複数の相手への通話にエスカレーションします。
- 2パーティのチャットのファイル転送、またはグループチャットの添付ファイル (Teams から Skype for Business、またはその逆) はサポートされません。
- Skype for Business の常設チャットとの相互運用性はありません。

これらすべての制限事項 (常設チャットを除く) については、1人のユーザーが会議を開始して、他のユーザーを招待して参加できるようにすることをお勧めします。 この回避策は、相互運用エスカレーションの基礎となります。

> [!Important]
> 簡単なチャット (IM) として開始されるのは、通話や臨時の会議にすばやくエスカレートされることがあります。 これらのシナリオはユーザビリティとユーザーエクスペリエンスにとって重要であることを理解しており、Skype for Business と Teams ユーザーの間で相互運用性のエクスペリエンスを継続的に進化させています。 最新の情報を確認してください。

この記事の内容を確認した後、「アップグレード[](https://aka.ms/SkypeToTeams-Interop)の[過程を選択](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)する」、「 [Skype for business との共存](coexistence-chat-calls-presence.md)」、「共存の設定[とアップグレードの設定](https://aka.ms/SkypeToTeams-SetCoexistence)を行う」を参照してください。説明.

## <a name="related-links"></a>関連リンク

[ビデオ: SfB と Teams の間で共存と相互運用性を管理する](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
