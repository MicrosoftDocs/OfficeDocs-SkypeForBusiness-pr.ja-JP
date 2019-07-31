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
ms.openlocfilehash: e29e6f62167527dced8121abdd213b891de2349b
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "35934631"
---
![プロジェクト定義ステージを強調したアップグレードの図](media/upgrade-banner-project-definition.png "プロジェクト定義ステージに重点を置いたアップグレードの段階")

この記事は、アップグレードが行われるプロジェクト定義ステージの一部であり、スポンサー協力とプロジェクトチームを作成して、プロジェクトの範囲、目標、ビジョンを定義した後に行うアクティビティです。 先に進む前に、次のアクティビティを完了していることを確認してください。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Microsoft Teams と Skype for Business の共存と相互運用性について

組織で Skype for Business を使用していて、チームで Skype for business を使用している場合、または Teams へのアップグレードを開始する場合、2つのアプリケーションの共存方法、相互運用方法、管理方法を理解することが重要です。Skype for Business から Teams への最終的なアップグレードについては、ユーザーの移行をお客様にご利用ください。

> [!Tip]
> [共存と相互運用性](https://aka.ms/teams-upgrade-coexistence-interop)の詳細については、次のセッションをご覧ください。
>
> また、アップグレード計画と実装を開始するために設計されたガイダンス、ベストプラクティス、およびリソースを共有するライブインタラクティブなワークショップに参加することもできます。
>
> 最初に[アップグレード](https://aka.ms/SkypeToTeamsPlanning)セッションの計画に参加してください。

## <a name="coexistence-of-teams-and-skype-for-business"></a>Teams と Skype for Business の共存

チームは、共同作業機能に加えて、チャット、通話、会議の機能を提供します。 チームの展開方法に応じて、これらの機能は、特定のユーザーに対して Skype for Business によって提供される機能と重複する可能性があります。 既定のモードでは、機能が重複するため、Skype for Business と共にチームを実行します。ただし、ユーザーは、これらの機能がユーザーに重複しないように設計されたいくつかの共存モードのいずれかを割り当てることができます (この場合、Teams と Skype for Business の間の相互運用性が利用可能になります)。

どのパスが自分の組織に適しているかを判断するために、以下で説明する共存モードを確認することをお勧めします。

> [!Important]
> 新しいテクノロジを導入したり、既存の使い慣れた Skype for Business 環境に変更を加えたりすることで、新しいビジネス上のメリットを提供し、ユーザーの混乱を防ぐことができます。 この記事で説明されている変更を実装する前に、ユーザーの準備を評価し、コミュニケーションとトレーニングの計画を実装することが必要です。 さらに、組織全体に実装する前に、選択したユーザーのグループに計画を試験的に適用することを強くお勧めします。

### <a name="islands-mode"></a>諸島モード

既定では、ユーザーは、プレゼンス、チャット、通話、会議などの類似した重複した機能を提供する2つの独立したソリューションとして、Skype for Business と共にチームを実行できます。 チームユーザーは、チームとチャネル、Office 365 のファイルへのアクセス、アプリケーションなどの新しいコラボレーション機能を利用することもできます。

この共存モード (**孤島**) では、各クライアントアプリケーションは独立したアイランドとして動作します。 Skype for Business は、Skype for business とチームとのやり取りをします。 ユーザーは、常に両方のクライアントを実行し、通信が開始されたクライアントでネイティブ通信できます。 このように、**孤島**モードでの相互運用性は不要です。

混乱または regressed の Skype for Business エクスペリエンスを回避するため、外部 (フェデレーション) 通信、PSTN 音声サービスと音声アプリケーション、Office の統合、その他のいくつかの統合は、引き続き Skype for Business で処理されます。

> [!Important]
> **島々**モードでは、フェデレーションされたユーザーからのすべてのメッセージ (組織外のユーザー) が Skype for business に配信されます。 [**チームのみ**] モードに切り替えると、組織外のすべてのメッセージが teams に配信されます。

> [!Tip]
> Skype for Business Online のお客様に推奨されるパスは、既定の**アイランド**モードから開始して、組織内のチームの導入を推進した後、すぐに**teams 専用**モードに移行することです。 オンプレミスおよびハイブリッドのお客様は、組織の**コラボレーションモードでの skype For business**の展開は、孤島ではなく開始点として、**チームのコラボレーションと会議モードでの skype for business**からの進捗管理において、必要に応じて、チームを採用する準備ができた時点で、[**チームのみ**] モードにします。

### <a name="skype-for-business-only"></a>Skype for Business のみ

この共存モードでは、ユーザーは、チャット、会議、通話機能のために、Teams ではなく、Skype for Business にとどまります。チームやチャネルには Teams は使用されません。 このモードは現在利用できます。ただし、現在の実装では、ユーザーのチームとチャネルは自動的に無効になりません。 これを実現するには、アプリのアクセス許可ポリシーを使って、チームとチャネルを非表示にします。

### <a name="teams-only"></a>Teams Only

Teams**のみ**のユーザー (*アップグレード*されたユーザーとも呼ばれます) は、teams のすべての機能にアクセスできます。 Skype for business クライアントは、アップグレードされていないユーザーまたは外部関係者によって開催された Skype for Business の会議に参加することができます。 アップグレードされたユーザーは、引き続き Skype for Business を使用している組織内の他のユーザーと通信することができます。チームと Skype for business の間の相互運用性機能を使用します (これらの Skype for Business ユーザーは、孤島モードになっていない場合)。;ただし、アップグレードされたユーザーは、Skype for Business チャット、通話、会議を開始することはできません。

組織の一部またはすべてのユーザーが、唯一のコミュニケーションとコラボレーションツールとして Teams を使用する準備ができたら、そのユーザーを**チーム専用**モードにアップグレードできます。 島々モードからアップグレードする場合は、アップグレードプロセスを開始する前に、まず組織全体でチームの導入を飽和させることをお勧めします。 これにより、孤島モードによって相互運用性が提供されないため、通信の中断のシナリオを回避できます。

チーム専用モードへの移行に関するその他の考慮事項については、「[チームのみモードの考慮事項](teams-only-mode-considerations.md)」を参照してください。

![Teams 確認メッセージのスクリーンショット](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "ユーザーがチーム専用ユーザーとしてアップグレードされた後に、特別モードで実行されている Skype For business クライアント")

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business とチームの共同作業

このモードを使用すると、引き続き Skype for Business で既存の投資を活用しながら、環境に Teams を導入することができます。 このモードでは、チャット、通話、会議機能のために Skype for Business を変更せずに、チームのコラボレーション機能 (チームとチャネル、Office 365 内のファイルへのアクセスなど) を追加します。 チームのコミュニケーション機能: プライベートなチャット、通話、会議のスケジュール設定は、このモードでは既定で無効になっています。 社内またはハイブリッド上の Skype for Business server の出発点を持つ組織は、ユーザーの通信性と予測性をユーザーに提供する必要がある場合は、このモードを、孤島モードの代わりとして考慮する必要があります。

### <a name="skype-for-business-with-teams-collaboration-and-meetings"></a>チームでの共同作業と会議を行った Skype for Business

この共存モードを使用すると、共同作業機能に加えて、組織のチーム会議機能の可用性を向上させることができるため、ユーザーは優れたチーム会議エクスペリエンスを活用することができます。議事録、翻訳、バックグラウンドブラーなどの革新的な機能と、モバイルデバイスやブラウザーを含むすべてのプラットフォームで優れたユーザーエクスペリエンスを提供します。

このモードでのチームおよびチャネルベースの会話に Teams を使用すると、ユーザーはチームを使用して会議をスケジュールおよび実施します。 プライベートチャットと通話は Skype for Business に残ります。 チームと Skype for Business では、プレゼンスの調整、自動ホールド/unhold、および両方のアプリケーションの HID デバイスのサポートなど、さまざまな機能を利用できます。 

この共存モードは、特に、エンタープライズ voip の Skype for Business オンプレミス展開のユーザーに適しています。チームへのアップグレードに時間がかかることがあり、できるだけ早く Teams の会議を活用したいと考えています。

> [!Note]
> 特定の共存モードで展開されると、チームと Skype for Business の[相互運用](#interoperability-of-teams-and-skype-for-business)が可能になり、ユーザーは互いにチャットしたり、通話を発信したり、組織内でチームへのアップグレード中に通信が流動的な状態に維持されるようになります。 共存モードは、相互運用性を制御します。 相互運用性を利用できるかどうかは、受信者の共存モードによって異なります。 たとえば、受信者がチャットを1つのクライアント (たとえば、Teams) でしか使用できないモードである場合は、通常、他のクライアント (この例では Skype for Business) を使用してチャットを開始したときに、チャットの相互運用性が利用可能になります。 一方、受信者が両方のクライアント (孤島モード) でチャットが利用可能なモードになっている場合、チャットでは相互運用性を利用できません。 メッセージは、イニシエーターがチャットを開始した同じクライアントの受信者によって受信されます。 そのため、島々モードでの適切なコミュニケーションには、チームの導入の鮮やかさが必要です。つまり、両方のユーザーが両方のクライアントを積極的に使って監視します。

> [!TIP]
> Skype for Business がまだ使用されているときに、チームで有効にする機能に基づいて推奨されるアップグレードモードを特定するには、 [skype To Teams アップグレードウィザード](https://aka.ms/SkypeToTeamsWizard)をご利用ください。

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
- _相互運用性のエスカレーション_操作では、ユーザーが高度な操作 (デスクトップの共有など) を実行できるようにする際に、クライアントが会議の作成を容易にして、ユーザーが参加して会議のエクスペリエンスを継続できるようにします。 会議は、アクションのイニシエーターのプラットフォームで作成されます。 このプラットフォームを使っていないユーザーまたはユーザーが、会議の参加リンクを受信します。 このリンクをクリックすると、互換性のあるクライアント (構成によっては、ブラウザー、web アプリ、またはフルクライアント) で会議に参加します。 Skype for Business からの相互運用エスカレーションには、最近のクライアントが必要です。 Teams からの相互運用エスカレーションは近日中にリリースされます。

### <a name="native-interop-experiences"></a>ネイティブの相互運用エクスペリエンス

ユーザーに割り当てられている共存モード (前述のとおり) に応じて、次のネイティブの相互運用機能を使用できます。

- Skype for Business ユーザーは、チームユーザーと1対1のチャットを行うことができます。その逆も可能です。 相互運用機能のチャットは、Teams クラウドサービスの一部である相互運用ゲートウェイを通じて行う必要があります (そのため、オンラインである必要があります)。 相互運用機能のチャットはプレーンテキストです。リッチテキストと絵文字はサポートされていません。 Teams および Skype for Business のユーザーには、その会話が相互運用スレッドであることが通知されます。

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

この記事の内容を確認した後、「アップグレード[](https://aka.ms/SkypeToTeams-Interop)の[過程を選択](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)する」、「 [Skype for business との共存](coexistence-chat-calls-presence.md)」、「共存の設定[とアップグレードの設定](https://aka.ms/SkypeToTeams-SetCoexistence)を行う」を参照してください。説明.

## <a name="related-links"></a>関連リンク

[ビデオ: SfB と Teams の間で共存と相互運用性を管理する](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
