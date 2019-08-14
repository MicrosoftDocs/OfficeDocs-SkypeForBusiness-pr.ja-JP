---
title: Microsoft Teams |アップグレード、孤島モード、相互運用ポリシー
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Skype for Business および Microsoft Teams の共存オプションと、Skype for Business と Teams の相互運用性について詳しく説明します。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d89eec1f643204750fb1c35845382639a7e04eb7
ms.sourcegitcommit: ab259764dc50bdd52efed3abb1d065ee19486946
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "36393475"
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

チームは、共同作業機能に加えて、チャット、通話、会議の機能を提供します。 チームの展開方法に応じて、これらの機能は、特定のユーザーに対して Skype for Business によって提供される機能と重複する可能性があります。 既定のモードでは、機能が重複するため、Skype for Business と共にチームを実行します。ただし、ユーザーには、これらの機能がユーザーに重複しないようにするために設計されたいくつかの共存モード (アップグレードモードとも呼ばれます) のいずれかを割り当てることができます (この場合、Teams と Skype for Business の間の相互運用性は利用可能です)。 たとえば、複雑なエンタープライズ Voip 展開を備えた、非常に多くの Skype for Business Server のオンプレミスのアセットがあり、ユーザーができるだけ早く最新の会議を楽しみたい場合は、最初に会議を評価することをお勧めします (下記を参照)。代替パス。

どのパスが自分の組織に適しているかを判断するために、次の共存モードを確認することをお勧めします。

> [!Important]
> 新しいテクノロジを導入したり、既存の使い慣れた Skype for Business 環境に変更を加えたりすることで、新しいビジネス上のメリットを提供し、ユーザーの混乱を防ぐことができます。 この記事で説明されている変更を実装する前に、ユーザーの準備を評価し、コミュニケーションとトレーニングの計画を実装することが必要です。 さらに、組織全体に実装する前に、選択したユーザーのグループに計画を試験的に適用することを強くお勧めします。

### <a name="islands-mode"></a>諸島モード

既定では、ユーザーは、プレゼンス、チャット、通話、会議などの類似した重複した機能を提供する2つの独立したソリューションとして、Skype for Business と共にチームを実行できます。 チームユーザーは、チームとチャネル、Office 365 のファイルへのアクセス、アプリケーションなどの新しいコラボレーション機能を利用することもできます。

この共存モード (**孤島**) では、各クライアントアプリケーションは独立したアイランドとして動作します。 Skype for Business は、Skype for business とチームとのやり取りをします。 ユーザーは、常に両方のクライアントを実行することを想定しており、通信が開始されたクライアントでネイティブ通信を行うことができます。 このように、**孤島**モードでの相互運用性は不要です。

混乱または regressed の Skype for Business エクスペリエンス、外部 (フェデレーション) 通信、PSTN 音声サービスと音声アプリケーション、Office 統合、USB デバイス用の HID コントロール、その他のいくつかの統合は、引き続き Skype で処理されます。Business の場合、**孤島**モードの Teams では利用できません。 電話システムは、**孤島**モードの Teams ではサポートされていません。このモードでは、エンタープライズボイスクライアントのみが Skype for Business になります。

> [!Important]
> **諸島**モードでは、フェデレーションされたユーザー (組織外のユーザー) からのすべてのメッセージと通話が Skype for business に配信されます。 [**チームのみ**] モードにアップグレードした後は、組織外からのすべてのメッセージと通話が teams に配信されます。

> [!Tip]
> Skype for Business Online のお客様に推奨されるパスは、既定の**アイランド**モードから開始して、組織内のチームの導入を推進した後、すぐに**teams 専用**モードに移行することです。 社内およびハイブリッドのお客様の場合、特に複雑な場合は、組織のグループ作業モードではなく、チームの**** コラボレーションモードで開始点として**skype for business**を展開すると、組織のグループ作業モードではなく、skype for business を使用することができます。 **チームのコラボレーションと会議**モード (つまり、会議の最初の会議モード)、適切な場合は [チーム**のみ**] モード。組織がチームを採用する準備ができたとき。

### <a name="skype-for-business-only"></a>Skype for Business のみ

この共存モードでは、ユーザーは、チャット、会議、通話機能のために、Teams ではなく、Skype for Business にとどまります。チームやチャネルには Teams は使用されません。 このモードは現在利用できます。ただし、現在の実装では、ユーザーのチームとチャネルは自動的に無効になりません。 これを実現するには、アプリのアクセス許可ポリシーを使って、チームとチャネルを非表示にします。

このモードは、チームの管理された展開を開始する前に使用することができます。これは、ユーザーが事前に構築された準備ができるようになる前にチームの使用を開始することを防止するため、または Skype for Business ユーザーのチーム会議で認証された参加を有効にする方法として、Teams のライセンス。

### <a name="teams-only"></a>Teams Only

Teams**のみ**のユーザー (*アップグレード*されたユーザーとも呼ばれます) は、teams のすべての機能にアクセスできます。 Skype for business クライアントは、アップグレードされていないユーザーまたは外部関係者によって開催された Skype for Business の会議に参加することができます。 アップグレードされたユーザーは、引き続き Skype for Business を使用している組織内の他のユーザーと通信することができます。この場合、チームと Skype for business の間の相互運用性機能を使用します (これらの Skype for Business ユーザーは、散在していません)。 **** モード)。 ただし、アップグレードされたユーザーは、Skype for Business チャット、通話、会議を開始することはできません。

組織の一部またはすべてのユーザーが、唯一のコミュニケーションとコラボレーションツールとして Teams を使用する準備ができたら、そのユーザーを**チーム専用**モードにアップグレードできます。 **島々**モードからアップグレードする場合は、アップグレードプロセスを開始する前に、まず組織全体でチームの導入を飽和させることをお勧めします。 これにより、**孤島**モードによって相互運用性が提供されないため、通信の中断のシナリオを回避できます。

**チーム専用**モードへの移行に関するその他の考慮事項については、「[チームのみモードの考慮事項](teams-only-mode-considerations.md)」を参照してください。

![Teams 確認メッセージのスクリーンショット](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "ユーザーがチーム専用ユーザーとしてアップグレードされた後に、特別モードで実行されている Skype For business クライアント")

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business とチームの共同作業

このモードを使用すると、引き続き Skype for Business で既存の投資を活用しながら、環境に Teams を導入することができます。 このモードでは、チャット、通話、会議機能のために Skype for Business を変更せずに、チームのコラボレーション機能 (チームとチャネル、Office 365 内のファイルへのアクセスなど) を追加します。 チームのコミュニケーション機能: プライベートなチャット、通話、会議のスケジュール設定は、このモードでは既定で無効になっています。

社内またはハイブリッドの Skype for Business Server の出発地点を持つ組織では、ユーザーの通信の相互運用性と予測性を実現する必要がある場合は、このモードを、**孤島**モードの代わりとして考慮する必要があります。Teams にアップグレードするための予測可能なタイムラインがあります (**孤島**モードでの導入による彩度に依存するのではありません)。

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>チームのコラボレーションと会議 (会議とも呼ばれます) を使用する Skype for Business

この共存モードを使用すると、共同作業機能に加えて、組織のチーム会議機能の可用性を向上させることができるため、ユーザーは優れたチーム会議エクスペリエンスを活用することができます。議事録、翻訳、バックグラウンドブラーなどの革新的な機能と、モバイルデバイスやブラウザーを含むすべてのプラットフォームで優れたユーザーエクスペリエンスを提供します。

このモードでのチームおよびチャネルベースの会話に Teams を使用すると、ユーザーはチームを使用して会議をスケジュールおよび実施します。 プライベートチャットと通話は Skype for Business に残ります。 チームと Skype for Business では、プレゼンスの調整、自動ホールド/unhold、および両方のアプリケーションの HID デバイスのサポートなど、さまざまな機能を利用できます。 アプリのアクセス許可ポリシーを使用して、必要に応じてチームとチャネルを非表示にすることができます。

この共存モードは、エンタープライズ Voip での Skype for Business オンプレミス展開の場合に特に便利です。チームへのアップグレードに時間がかかる可能性があるため、できるだけ早く Teams の会議を活用する必要があります。

> [!Note]
> **孤島**以外の共存モードで展開すると、Teams と Skype for business は[相互運用](#interoperability-of-teams-and-skype-for-business)が可能になり、ユーザーは互いにチャットして通話できるようになり、アップグレード中も組織全体でその通信が流動的な状態に維持されます。Teams への旅。 共存モードは、相互運用性を制御します。 相互運用性を利用できるかどうかは、受信者の共存モードによって異なります。 たとえば、受信者がチャットを1つのクライアント (たとえば、Teams) でしか使用できないモードである場合は、通常、他のクライアント (この例では Skype for Business) を使用してチャットを開始したときに、チャットの相互運用性が利用可能になります。 一方、受信者が両方のクライアント (孤島モード) でチャットが利用できるモードになっている場合、チャットでは相互運用性を利用できません。 メッセージは、イニシエーターがチャットを開始した同じクライアントの受信者によって受信されます。 そのため、**島々**モードでの適切なコミュニケーションには、チームの導入の鮮やかさが必要です。つまり、両方のユーザーが両方のクライアントを積極的に使って監視します。

> [!TIP]
> Skype for Business がまだ使用されているときに、チームで有効にする機能に基づいて推奨されるアップグレードモードを特定するには、 [skype To Teams アップグレードウィザード](https://aka.ms/SkypeToTeamsWizard)をご利用ください。

共存モード、前提条件、および管理の詳細については、「[チームと Skype For business を組み合わせて使用する組織向けの移行と相互運用性のガイダンス](https://aka.ms/SkypeToTeams-Interop)」および「[共存とアップグレードの設定](https://aka.ms/SkypeToTeams-SetCoexistence)」を参照してください。

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|判断ポイント|<ul><li>組織とユーザーのニーズに最も適合する共存モード</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|次の手順|<ul><li>アップグレードに最適な方法を選択します。</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Teams と Skype for Business の相互運用性

相互運用性とは、チームと Skype for Business ユーザーが同じ組織内でチームと skype for business の間で通信できる機能です。

相互運用性は、受信者の共存モード (アップグレードモードとも呼ばれます) によって制御されます。 受信者が**諸島**モードの場合、相互運用性はありません。

### <a name="native-interop-and-interop-escalation"></a>ネイティブの相互運用性と相互運用エスカレーション

相互運用エクスペリエンスには、ネイティブと相互運用によるエスカレーションという2つの種類があります。

- ユーザーが現在使用しているクライアントで_ネイティブの相互運用_エクスペリエンスが発生します。 1人のユーザーは、Teams の Skype for Business クライアントに表示されます。 ネイティブの相互運用機能によって、他のクライアントに伝達されることはありません。ユーザーは、現在使用しているクライアントで会話を行うことができます。 ネイティブの相互運用エクスペリエンスは、1対1のチャットと通話です。
- _相互運用性のエスカレーション_操作では、ユーザーが高度な操作 (デスクトップの共有など) を実行できるようにする際に、クライアントが会議の作成を容易にして、ユーザーが参加して会議のエクスペリエンスを継続できるようにします。 会議は、アクションのイニシエーターのプラットフォームで作成されます。 このプラットフォームを使っていないユーザーまたはユーザーが、会議の参加リンクを受信します。 このリンクをクリックすると、互換性のあるクライアント (構成によっては、ブラウザー、web アプリ、またはフルクライアント) で会議に参加します。 Skype for Business からの相互運用エスカレーションには、最近のクライアントが必要です。 Teams からの相互運用エスカレーションが利用できるようになりました。 両方は、テナント内の相互運用性のエクスペリエンスと、フェデレーション通信のクロステナントの両方でサポートされています。

### <a name="native-interop-experiences"></a>ネイティブの相互運用エクスペリエンス

ユーザーに割り当てられている (前に説明した) 共存モードに応じて、次のネイティブの相互運用機能を使用できます。

Skype for Business ユーザーは、チームユーザーと1対1のチャットを行うことができます。その逆も可能です。 相互運用機能のチャットは、Teams クラウドサービスの一部である相互運用ゲートウェイを通じて行う必要があります (そのため、オンラインである必要があります)。 相互運用機能のチャットはプレーンテキストです。リッチテキストと絵文字はサポートされていません。 Teams および Skype for Business のユーザーには、その会話が相互運用スレッドであることが通知されます。

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business ユーザーは、1対1の音声通話とビデオ通話を Teams ユーザーに対して行うことができます。また、その逆も可能です。

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Skype for Business のオンプレミス展開での相互運用エクスペリエンスには、オンプレミス環境が Office 365 Skype for Business のハイブリッドモードになっている必要があります。 詳細については、「[移行と相互運用性のガイダンス](https://aka.ms/SkypeToTeams-Interop)」を参照してください。

これらの相互運用機能は、次のいずれかの共存モードが割り当てられているユーザーが利用できます。**チームコラボレーションを備えた skype For business**、**チームのコラボレーションと会議**、skype for business **ビジネスのみ**、または**チームのみ**。 **孤島**モードでは、ユーザーに対する相互運用性はありません。

### <a name="native-interop-experience-limitations"></a>ネイティブの相互運用機能のエクスペリエンスに関する制限事項

プロトコルとテクノロジには違いがあるため、すべての機能をネイティブにサポートすることはできません。 具体的には、次の機能は使用できません。

- マークダウン、rich text、および完全な絵文字セットは、Teams または Skype for Business ではサポートされていません。 チームチャットの作成ボックスのその他のネイティブ機能はサポートされていません。
- Teams と Skype for Business の間の画面共有 (デスクトップまたはアプリの共有) は、ネイティブではサポートされません。 ただし、相互運用エスカレーションによってサポートされます。
- Teams のグループチャット (複数パーティの会話) には、Teams を使用している参加者のみを含めることができます。
- Skype for Business の複数パーティの IM 会話 (グループチャット) には、Skype for Business を使用している参加者のみを含めることができます。 ただし、複数当事者への相互運用エスカレーションは、Skype for Business から入手できます。
- 進行中のピアツーピアの音声通話またはビデオ通話を、Teams と Skype for Business の両方でサポートされていない複数の相手への通話にエスカレーションします。
- 2パーティのチャットのファイル転送、またはグループチャットの添付ファイル (Teams から Skype for Business、またはその逆) はサポートされません。
- Skype for Business の常設チャットとの相互運用性はありません。

これらすべての制限事項 (常設チャットを除く) については、1人のユーザーが会議を開始して、他のユーザーを招待して参加できるようにすることをお勧めします。

この回避策は、相互運用エスカレーションの基礎となります。 特に、画面共有とマルチパーティへのエスカレーションはネイティブでは実現できませんが、相互運用エスカレーションによってサポートされます。

### <a name="interop-escalation-experiences"></a>相互運用エスカレーションのエクスペリエンス

相互運用エスカレーションは、ネイティブの相互運用機能と、会議への管理されたエスカレーションによって構成されます。 会議では、どのクライアントを使用しているかにかかわらず、あらゆるユーザーに対して豊富なエクスペリエンスを提供できます。

チームユーザーが相互運用エスカレーションを開始すると、Teams 会議が作成されます。 Skype for Business ユーザーによってトリガーされると、Skype for Business 会議が作成されます。 どちらの場合も、作成された会議は now 会議に**なり**、ユーザーの予定表には反映されません。
 
一方の相手は、そのリンクをクリックすると、相互運用チャットと結合によって会議の参加リンクを受け取ります。 Skype for Business ユーザーが Teams アカウントを持っていて、Teams ユーザーによって招待された場合は、承認済みの会議に参加します。 それ以外の場合は、匿名の参加者として参加します。 一方、チームユーザーはほとんどの場合、skype for business アカウントと skype for Business クライアントを使用して、認証された参加者として Skype for business 会議に参加できますが、skype を使用するなど、匿名の参加者として参加することもあります。会議アプリ。

会議に参加すると、デスクトップやコンテンツの共有、ファイル共有や転送、他の参加者の追加など、会議でサポートされているすべてのアクティビティを実施できます。

#### <a name="interop-escalation-from-skype-for-business"></a>Skype for Business からの相互運用エスカレーション

Skype for Business からの相互運用性と相互運用性のエスカレーションは、C2R 年7月の2019ビルドで更新されました。 以前は、Skype for Business では、リモートの利用者が Teams を使用していたことについて事前に認識していませんでした。 これは、セッションが確立された後に受信したシグナリングからの surmised のみを行います。

応答が相互運用ゲートウェイから送信されたことを通知された場合は、その相手が Skype for Business を使用していなかったことを示す黄色のビジネスバー (バナー) が表示されます。 サービスの進化により、Skype for Business ユーザーは、実際の**チームのみ**のユーザーではなく、クラウドボイスメールサービスやその他のクラウド音声サービスに接続したときに、ビジネスバーが表示されるという誤検知が発生しました。
 
これらの誤検知を防ぐために、相手が実際のユーザー**のみ**を対象としている場合に、プレゼンスサービスが Skype for business クライアントに通知されるようになりました。 これにより、Skype for Business は、そのスレッドが作成された後に相互運用スレッドを作成する必要があることを認識し、[会話] ウィンドウを相互運用に固有のものとして扱うことができます。

![Skype for Business ユーザーとの相互運用会話を作成するための Teams メッセージのスクリーンショット](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Skype for Business ユーザーがデスクトップを共有しようとしている場合は、会議を開始し、手順に従って案内することが通知されます。

![Teams ユーザーとの会議を開始するための Teams メッセージのスクリーンショット](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

一方で、Teams ユーザーは、会議へのリンクを含む着信チャットメッセージを受け取り、参加するように指示されます。

Skype for Business 会議へのこのエスカレーションは、テナント内の相互運用と、クロステナントフェデレーション通話とチャットの両方で利用できます。 これは既定でオンになっており、管理者がプロビジョニングする必要のある設定はありません。

#### <a name="interop-escalation-from-teams"></a>Teams からの相互運用エスカレーション

チームユーザーが、Skype for Business ユーザーまたはクロステナント相互運用フェデレーションスレッドで、テナント内の相互運用スレッドでデスクトップ共有ボタンを選択したときに、チームからチーム会議への相互運用エスカレーションが利用できるようになりました。 相互運用エスカレーションは、1:1 チャットでの会話または1:1 通話からサポートされています。

この機能は、Windows 用の Teams デスクトップクライアント、Teams デスクトップクライアント for Mac、コンテンツ共有がサポートされているブラウザー上の Teams web クライアントでサポートされていますが、Skype for Business クライアントバージョンでの通信はサポートされています。

相互運用性スレッドおよびフェデレーションの相互運用性スレッドでは、Teams ユーザーは、コンテンツ共有を開始するためのコントロール (button) を持つようになりました。 Teams ユーザーがボタンを選ぶと、コンテンツを共有するように通知する追加のメニューが表示され、チーム会議を開始する必要があります。

ユーザーが通話中の場合は、チームと Skype for Business の間の現在の通話が、Teams 会議に参加したときに終了されることを示す警告もメニューに表示されます。 お客様が選択した場合は、承認前に Skype for Business ユーザーに警告することができます。

![Skype for Business ユーザーとの会議を共有するための Teams メッセージのスクリーンショット](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

承諾すると、それらのユーザーは Teams 会議に参加します。会議の共有トレイから共有を開始する必要があります。
 
一方で、Skype for Business ユーザーは、会議へのリンクを含むチャットメッセージを受信し、参加するように指示されます。

このエスカレーションチーム会議へのエスカレーションは、テナント内の相互運用およびクロステナントフェデレーション通話とチャットの両方で利用できます。 これは既定でオンになっており、管理者がプロビジョニングする必要のある設定はありません。 ただし、管理者が``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy``に``$false``設定している場合は、ユーザーに対して無効になります。

この記事の内容を確認した後、「アップグレード[](https://aka.ms/SkypeToTeams-Interop)の[過程を選択](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)する」、「 [Skype for business との共存](coexistence-chat-calls-presence.md)」、「共存の設定[とアップグレードの設定](https://aka.ms/SkypeToTeams-SetCoexistence)を行う」を参照してください。説明.

## <a name="related-links"></a>関連リンク

[ビデオ: SfB と Teams の間で共存と相互運用性を管理する](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
