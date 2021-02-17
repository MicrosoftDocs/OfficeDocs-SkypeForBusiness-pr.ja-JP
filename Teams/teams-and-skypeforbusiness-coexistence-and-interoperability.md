---
title: Skype for Business と Microsoft Teams の相互運用性
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Skype for Business と Microsoft Teams の共存オプションの詳細、および Skype for Business と Teams 間の相互運用性。
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
ms.openlocfilehash: 7ffc673ade43e8acdb258c9364b3023ba21da2a7
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260349"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Microsoft Teams と Skype for Business の共存と相互運用性を理解する

![プロジェクトの定義ステージが強調表示されたアップグレード行程図](media/upgrade-banner-project-definition.png "「プロジェクトの定義」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード行程の「プロジェクトの定義」段階の一部です。 後でスポンサーの連立とプロジェクト チームを作成し、プロジェクトの範囲、目標、計画を定義します。 続く前に、次のアクティビティを完了したと確認します。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)

組織で現在 Skype for Business を使用している場合、または Teams へのアップグレードを開始する場合、または Skype for Business と一緒に Teams を使用し始める場合は、次の項目を理解することが重要です。

- 2 つのアプリケーションが共存する方法。
- 相互運用の方法と時間。
- Skype for Business から Teams への最終的なアップグレードまで、ユーザーの移行を管理する方法。

> [!Tip]
> [共存と相互運用性](https://aka.ms/teams-upgrade-coexistence-interop)の詳細を説明するセッションをご視聴ください。
>
> また、ライブで対話型のワークショップに参加して、アップグレードの計画と実装を開始するように設計されたガイダンス、ベスト プラクティス、リソースを共有することができます。
>
> アップグレードを開始するには、最初に「[アップグレードの計画](https://aka.ms/SkypeToTeamsPlanning)」セッションにご参加ください。

## <a name="coexistence-of-teams-and-skype-for-business"></a>Teams と Skype for Business の共存

 Teams は、共同作業機能、チャット、通話、会議機能を提供します。 Teams の展開方法によっては、これらの機能が特定のユーザーに対して Skype for Business によって提供される機能と重複する場合があります。 既定のモードでは、機能が重複して Skype for Business と共に Teams を実行します。 ただし、これらの機能がユーザーに重ならないように設計された複数の共存モード (アップグレード モードとも呼ばれる) の 1 つをユーザーに割り当てることができます (その場合、Teams と Skype for Business 間の相互運用性を利用できます)。 たとえば、複雑な エンタープライズ VoIP 展開を持つオンプレミスの重要な Skype for Business Server 資産があるが、ユーザーが可能な限り迅速に最新の会議を利用する必要がある場合は、代替パスとして会議 [を最初](meetings-first.md) に評価することができます。

どのパスが組織に一番適しているかを判断するために、以下の共存モードを確認することをお勧めします。

> [!Important]
> 新たな優れたビジネス上のメリットを提供しつつ、新しいテクノロジを導入したり、既存の馴染みのある Skype for Business 環境を変更したりする場合、ユーザーが混乱する場合があります。 この記事で説明する変更を実行する前に、時間をかけてユーザーの準備状況を評価し、コミュニケーションおよびトレーニングの計画を実施するようにしてください。 また、計画は、組織全体に実装する前に、選択したユーザーのグループで実験運用することを強くお勧めします。

### <a name="islands-mode"></a>アイランド モード

既定では、ユーザーは Skype for Business と一緒に Teams を実行し、類似した重複する機能を提供する 2 つの個別のソリューションとして実行できます。 プレゼンス、チャット、通話、会議などの機能があります。 Teams ユーザーは、チームやチャネルなどの新しいコラボレーション機能、Microsoft 365 または Office 365 のファイルへのアクセス、アプリケーションを利用することもできます。

「**アイランド**」と呼ばれるこの共存モードでは、各クライアント アプリケーションが別個のアイランド (島) として動作します。 Skype for Business は Skype for Business とやり取りし、Teams は Teams とやり取りします。 ユーザーは、両方のクライアントをすべての時点で実行すると想定され、通信を開始したクライアントでネイティブに通信できます。 そのため、Islands モードで相互運用性を確保する **必要** はありません。

Skype for Business の操作環境が混乱したり、再表示されるのを避けるために、Skype for Business は Teams の諸島モードでは処理されない次の統合を **処理** します。

- 外部 (フェデレーション) 通信。
- PSTN 音声サービスと音声アプリケーション、Office。
- USB デバイスの HID コントロール。
- その他のいくつかの統合。  

電話システムは、Teams の諸島モードでは **サポート** されていません。 **Islands** モードでは、クライアントが Skype for Business エンタープライズ VoIPサポートされていません。

> [!Important]
> [**アイランド**] モードでは、フェデレーション ユーザー (組織外のユーザー) からのすべてのメッセージと通話は、Skype for Business に配信されます。 [**Teams のみ**] モードにアップグレードすると、組織の外部からのすべてのメッセージと通話が Teams に配信されます。

> [!Tip]
> Skype for Business Online を使用中のお客様の場合、最初は既定の [**アイランド**] モードを使用し、組織内で Teams の導入完了を図り、その後、迅速に [**Teams のみ**] モードに移行することをお勧めします。 オンプレミスおよびハイブリッドのお客様は、その環境が複雑な場合は特に、出発点として [**アイランド**] モードではなく [**Skype for Business と Teams のコラボレーション**] モードを展開し、組織で Teams の導入準備が整い次第、(状況に応じて) [**Skype for Business と Teams のコラボレーションと会議**] モード (Meetings First のことです) および [**Teams のみ**] モードに進むという方法が有効な場合があります。

### <a name="teams-only"></a>Teams のみ

「**Teams のみ**」ユーザー (*アップグレード済み* ユーザーとも呼ばれます) は、Teams のすべての機能にアクセスできます。 これらのユーザーは、アップグレード済みではないユーザーや外部関係者によって開催される Skype for Business の会議に参加するために Skype for Business クライアントを残しておくことができます。 アップグレードしたユーザーは、Teams と Skype for Business の間の相互運用性機能を使用して(Skype for Business ユーザーが諸島モードではない場合)、引き続きSkype for Business を使用している組織内の他のユーザーと通信できます。 ただし、アップグレード済みユーザーは、Skype for Business のチャット、通話、会議を開始することはできません。

一部またはすべてのユーザーが Teams を通信および共同作業ツールとして使用する準備ができたら、それらのユーザーを **Teams のみモードにアップグレード** します。 Islands モードからアップグレードする場合は、アップグレード プロセスを開始する前に、まず組織全体で Teams の導入を飽和状態に設定してください。 この導入により、Islands モードでは相互運用性が提供されないため、通信シナリオが壊れるのを回避できます。

Teams のみモード **の** 場合、Teams は SIP/Tel プロトコルの既定のアプリです。 通話またはチャット用の Outlook のユーザーの連絡先カード内のリンクは、Teams によって処理されます。

Teams Only モードへの移行に関するその他の考慮事項については **、「Teams** のみモードに関する考慮事項」 [を参照してください](teams-only-mode-considerations.md)。

![Teams の確認メッセージのスクリーン ショット](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "ユーザーが Teams 専用ユーザーとしてアップグレードされた後、特別なモードで実行されている Skype for Business クライアント")

### <a name="skype-for-business-only"></a>Skype for Business のみ

この共存モードでは、ユーザーはチャット、会議、通話機能のために Teams ではなく Skype for Business に残り、チームやチャネルに Teams を使用しません。 このモードは現在使用できます。ただし、現在の実装では、チームとチャネルはユーザーに対して自動的にオフになりません。 これは、アプリ セットアップ ポリシーを使用してチームとファイルを非表示にすることで実現できます。

このモードは、Teams の管理された展開を開始する前に使用して、ユーザーが準備を構築する前に Teams を使用し始めから始めない場合に使用できます。 このモードは、ユーザーが Teams のライセンスを取得している場合に、Skype for Business ユーザーの Teams 会議に認証された参加を有効にする方法です。

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business と Teams のコラボレーション

このモードを使用して、Skype for Business への既存の投資を引き続き使用しながら、環境に Teams を導入します。 チャット、通話、会議の機能については、Skype for Business を変更しないでください。 Teams の共同作業機能を追加する:

- チームとチャネル。
- Microsoft 365 または Office 365 のファイルにアクセスします。
- アプリケーション。 Teams のコミュニケーション機能 (プライベート チャット、通話、会議のスケジュール設定)。

このモードでは、Teams のプライベート チャット、通話、および会議のスケジュール設定は既定でオフになっています。

オンプレミスまたはハイブリッドの Skype for Business Server を開始点とする組織は、コミュニケーションの相互運用性と予測可能性をユーザーに提供する場合、または ([**アイランド**] モードでの導入の浸透に頼る代わりに) ユーザーの Teams へのアップグレードを予測可能なタイムラインに沿って行う場合は、このモードを [**アイランド**] モードの代わりに使用することを検討してください。

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business と Teams のコラボレーションと会議 (Meetings First とも呼ばれます)

この共存モードを使用して、組織内の Teams 会議とコラボレーション機能の可用性を加速します。 共存モードを使用すると、ユーザーは優れた Teams 会議エクスペリエンスを利用できます。

- 優れた品質。
- トランスクリプションと翻訳。
- 背景のぼかし。
- モバイル デバイスやブラウザーなど、すべてのプラットフォームで優れたユーザー エクスペリエンスを提供します。

このモードでは、Teams はチームやチャネル ベースの会話に使用される他、ユーザーが会議のスケジュールを設定して実施するのにも Teams が使用されます。 プライベート チャットと通話は引き続き Skype for Business で行います。 Teams と Skype for Business は、プレゼンスの調整、自動保留/ホールド解除、両方のアプリケーションでの HID デバイス のサポートなど、さまざまな "より優れた" 機能を利用できます。 必要に応じて、アプリセットアップ ポリシーを使用して、チームとチャネルを非表示にできます。

この共存モードは、Skype for Business を展開している組織に特に便利な機能エンタープライズ VoIP。 これらの組織は、Teams へのアップグレードに少し時間がかかる可能性が高く、できるだけ早く優れた Teams 会議の恩恵を受けしたいと考えています。

> [!TIP]
> Skype for Business の使用が継続している場合に、 Teams で有効にしたい機能に基づき推奨されるアップグレード モードを特定するには、[Skype から Teams へのアップグレード ウィザード](https://aka.ms/SkypeToTeamsWizard)を使用します。

共存モード、前提条件、および管理の詳細については[、「Skype for Business](https://aka.ms/SkypeToTeams-Interop)と共に Teams を使用する組織の移行と相互運用性のガイダンス」および「共存とアップグレードの設定」を参照[してください。](https://aka.ms/SkypeToTeams-SetCoexistence)

|意思決定ポイント アイコン |アイコンの定義 |説明 |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|判断ポイント|<ul><li>組織とユーザーのニーズに最も適した共存モード</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|次の手順|<ul><li>アップグレード行程での最適なアプローチを選択する。</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Teams と Skype for Business の相互運用性

相互運用とは、同じ組織内の Teams ユーザーと Skype for Business ユーザーが Teams と Skype for Business の間で通信できるようにする機能です。

相互運用は、受信者の共存モード (アップグレード モードとも呼ばれます) によって制御されます。 受信者が [**アイランド**] モードの場合、相互運用性はありません。

> [!Note]
> [**アイランド**] 以外のいずれかの共存モードで展開すると、Teams と Skype for Business では [相互運用](#interoperability-of-teams-and-skype-for-business)が可能になります。これにより、アプリ間でのユーザー同士のチャットや通話がサポートされ、Teams へのアップグレードの行程期間中、円滑なコミュニケーションを組織全体で維持できます。 相互運用性は、共存モードにより制御されます。 受信者の共存モードにより、相互運用性を利用できるかどうかが決まります。 たとえば、受信者のモードが、チャットを 1 つのクライアントでのみ使用できるモード (Teams であるとします) である場合、発信者が別のクライアント (この場合は、Skype for Business) を使用してチャットを開始した場合に、チャットの相互運用性を利用できます。 一方、受信者が両方のクライアントでチャットを利用できるモード (諸島モード) の場合、チャットの相互運用性は利用できません。 受信者がメッセージを受信する際は、発信者がチャットを開始した際に使用したものと同じクライアントを使用して受信されます。 したがって、[**アイランド**] モードでコミュニケーションを正常に行うには、Teams の導入が行き渡っている必要があります。つまり、すべてのユーザーが、両方のクライアントをアクティブに使用して監視している状態です。

> [!Note]
> **最新の共存環境を使用するには、クライアント バージョンがユーザーの展開チャネルで利用可能な最新Office必要があります。**

### <a name="native-interop-and-interop-escalation"></a>ネイティブ相互運用と相互運用エスカレーション

相互運用エクスペリエンスには、ネイティブ相互運用と相互運用エスカレーションの 2 種類があります。

- _ネイティブ相互運用_ は、ユーザーがその時点で使用しているクライアントにおいて実行されます。 1 人のユーザーが Skype for Business クライアント内に存在し、もう 1 人は Teams 内にいる場合です。 ネイティブの相互運用機能のエクスペリエンスでは、通信に他のクライアントに移動しません。 ユーザーは、現在使用しているクライアントで会話を行う可能性があります。 ネイティブ相互運用エクスペリエンスは、1 対 1 のチャットと通話です。
- _相互運用エスカレーション_ エクスペリエンスでは、ユーザー行う高度な操作 (デスクトップの共有など) のサポートの一環として、クライアントでの会議の作成が容易になります。ユーザーはこの会議に参加して、相互運用エスカレーション エクスペリエンスを会議内で継続させられます。 会議は、操作を開始したユーザーのプラットフォームに作成されます。 そのプラットフォームに参加していないユーザーは、会議参加リンクを受け取る。 このリンクをクリックすると、互換性のあるクライアント (構成に基づいて、ブラウザー、Web アプリ、フル クライアントのいずれか) で会議に参加できます。 Skype for Business からの相互運用エスカレーションには、最新のクライアントが必要です。 Teams から相互運用エスカレーションを利用できるようになりました。 いずれのエスカレーションも、テナント内の相互運用エクスペリエンス、およびテナント間のフェデレーション コミュニケーションでサポートされます。

### <a name="native-interop-experiences"></a>ネイティブ相互運用エクスペリエンス

前述のように、ユーザーに割り当てられている共存モードに基づいて、以下のネイティブ相互運用エクスペリエンスを使用できます。

Skype for Business ユーザーと Teams ユーザーは 1 対 1 のチャットを行えます。 相互運用チャットは、Teams クラウド サービスの一部である相互運用ゲートウェイを経由する必要があります (そのため、オンラインでのみ存在します)。 相互運用チャットはプレーン テキストです。リッチ テキストと絵文字はサポートされていません。 Teams と Skype for Business のユーザーには、相互運用による会話であることが通知されます。

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business ユーザーは Teams ユーザーに対して 1 対 1 の音声通話とビデオ通話を行い、Teams ユーザーは同じ操作を行います。

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Skype for Business のオンプレミス展開との相互運用では、オンプレミス環境が Microsoft 365 または Office 365 Skype for Business とのハイブリッド モードである必要があります。 詳細については、「[移行と相互運用に関するガイドライン](https://aka.ms/SkypeToTeams-Interop)」を参照してください。

これらの相互運用エクスペリエンスは、[**Skype for Business と Teams のコラボレーション**]、[**Skype for Business と Teams のコラボレーションと会議**]、[**Skype for Business Only のみ**]、および [**Teams のみ**] の共存モードが割り当てられているユーザーが利用でき、これらのユーザー間で使用できます。 [**アイランド**] モードのユーザーの場合、相互運用性はありません。

### <a name="native-interop-experience-limitations"></a>ネイティブ相互運用エクスペリエンスの制限事項

プロトコルやテクノロジの違いにより、すべての機能をネイティブにサポートすることはできません。 具体的には、次の機能は使用できません。

- Markdown、リッチ テキスト、および完全な絵文字セットは、Teams または Skype for Business ではサポートされていません。 Teams チャットの作成ボックスのその他のネイティブ機能はサポートされていません。
- Teams と Skype for Business 間の画面共有 (デスクトップまたはアプリ共有) はネイティブではサポートされていません。 ただし、相互運用エスカレーションを使用する場合にはサポートされます。
- Teams のグループ チャット (複数による会話) には、Teams を使用している参加者のみが加わることができます。
- Skype for Business の複数による IM 会話 (グループ チャット) には、Skype for Business を使用している参加者のみが加わることができます。 ただし、Skype for Business からは複数での会話に相互運用エスカレーションを利用できます。
- 進行中のピアツーピア音声通話またはビデオ通話を、Teams と Skype for Business の両方のユーザーが関与するマルチパーティ通話にエスカレーションする機能はサポートされていません。
- Teams から Skype for Business への 2 者チャット、またはグループ チャット内の添付ファイルのファイル転送 (またはその逆) はサポートされません。
- Skype for Business 常設チャットには相互運用性はありません。

(常設チャットを除く) これらすべての制限事項に関しては、考えられる 1 つの回避策として、1 人のユーザーが会議を開始し、それに参加するよう他のユーザーを招待するという方法があります。

この回避策が、相互運用エスカレーションの基礎となっています。 特に、画面の共有および複数ユーザーへのエスカレーションはネイティブには実行できませんが、相互運用エスカレーションによってサポートされています。

### <a name="interop-escalation-experiences"></a>相互運用エスカレーション エクスペリエンス

相互運用エスカレーションは、ネイティブ相互運用機能を、会議への管理されたエスカレーションを使用して補完したものです。 会議では、ユーザーが所有しているクライアントに関係なく、だれもが豊富な機能を利用できます。

Teams ユーザーにより相互運用エスカレーションがトリガーされると、Teams 会議が作成されます。 それをトリガーしたのが Skype for Business ユーザーであった場合は、Skype for Business 会議が作成されます。 どちらの場合も、作成された会議は [今すぐ会議] 会議で、ユーザーの予定表には反映されません。

相手のユーザーは、相互運用チャットで会議参加リンクを受け取り、そのリンクをクリックすると参加できます。 Skype for Business ユーザーが Teams アカウントを持っていて Teams ユーザーによって招待されると、認証された状態で会議に参加します。 それ以外の場合は、匿名の参加者として参加します。 反対に、ほとんどの Teams ユーザーには必ず Skype for Business アカウントと、Skype for Business 会議に認証された参加者として使用できる Skype for Business クライアントがありますが、Skype 会議アプリを使用する場合など匿名の参加者として参加することもできます。

会議に参加したユーザーは、デスクトップやコンテンツの共有、ファイルの共有や転送、他の参加者の追加など、会議でサポートされるすべてのアクティビティを実行できます。

#### <a name="interop-escalation-from-skype-for-business"></a>Skype for Business からの相互運用エスカレーション

Skype for Business からの相互運用と相互運用エスカレーションは、月次 C2R の 2019 年 7 月ビルドで更新されました。 以前は、Skype for Business では、リモート ユーザーが Teams を使用していることを事前に認識できませんでした。 セッションが確立された後に受信した信号に基づいて推測されるだけでした。

応答が相互運用ゲートウェイから来たこと、またはゲートウェイを経由したことを信号が示している場合、そのユーザーが Skype for Business を使用していないことを示す黄色の ビジネス バー (バナー) が表示されます。 サービスの進化に伴い、実際の **Teams のみ** ユーザーに接続したときではなく、クラウド ボイスメール サービスや他のクラウド ボイス サービスに接続した場合にこのビジネス バーが Skype for Business ユーザーに表示されるようになり、誤検知が発生していました。

こうした誤検知を防ぐために、プレゼンス サービスでは、相手のユーザーが実際に **Teams のみ** ユーザーである場合に Skype for Business クライアントに通知するようになりました。 これにより、会話ウィンドウが作成されてしまう前に相互運用会話および相互運用専用の会話ウィンドウを作成する必要があることを Skype for Business に認識させられます。

![Skype for Business ユーザーとの相互運用会話を作成するための Teams メッセージのスクリーンショット](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Skype for Business ユーザーがデスクトップを共有しようとすると、会議が始まることが通知され、手順が案内されます。

![Teams ユーザーとの会議を開始する Teams メッセージのスクリーンショット](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

それと同時に、Teams ユーザーには会議へのリンクが含まれたチャット メッセージが届き、参加するためのガイドが示されます。

Skype for Business 会議へのこのエスカレーションは、テナント内の相互運用と、テナント間のフェデレーション通話とチャットで利用できます。 これは既定で有効になっており、管理者がプロビジョニングする必要のある設定はありません。

#### <a name="interop-escalation-from-teams"></a>Teams からの相互運用エスカレーション

Teams から Teams 会議への相互運用エスカレーションが、Skype for Business ユーザーとのテナント内相互運用スレッドにある、またはテナント間相互運用フェデレーション スレッドにあるデスクトップ共有ボタンを Teams ユーザーが選択すると利用できるようになりました。 相互運用エスカレーションは、1 対 1 のチャット会話または 1 対 1 の通話でサポートされています。

この機能は、Windows 用の Teams デスクトップ クライアント、Mac 用の Teams デスクトップ クライアント、コンテンツ共有がサポートされているブラウザー上の Teams Web クライアントでサポートされています。すべてのバージョンの Skype for Business クライアントと通信できます。

相互運用スレッドとフェデレーション相互運用スレッドで、Teams ユーザーにコンテンツ共有を開始するためのコントロール (ボタン) が表示されるようになりました。 Teams ユーザーがこのボタンを選択すると、コンテンツ共有や、Teams 会議を開始する必要があることを知らせる追加メニューが表示されます。

ユーザーが通話中の場合は、Teams と Skype for Business 間で行われている現在の通話が、Teams 会議に参加すると終了することも警告されます。 ユーザーが選択した場合は、承諾する前に Skype for Business ユーザーに警告を表示できます。

![Skype for Business ユーザーと会議を共有するための Teams メッセージのスクリーンショット](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

承諾すると、Teams 会議に参加できます。会議の共有トレイから共有を開始する必要があります。

一方、Skype for Business ユーザーは、会議へのリンクを含む着信チャット メッセージを受信し、参加するためのガイドが示されます。

Teams 会議へのこのエスカレーションは、テナント内の相互運用と、テナント間のフェデレーション通話とチャットで利用できます。 これは既定で有効になっており、管理者がプロビジョニングする必要のある設定はありません。 ただし、管理者が ``CsTeamsMeetingPolicy`` の ``-AllowPrivateMeetNow`` を ``$false`` に設定すると、ユーザーに対して無効になります。

この記事を確認した後は、次の関連記事を参照してください。

- [アップグレードの行程を選択する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [移行と相互運用性のガイダンス](https://aka.ms/SkypeToTeams-Interop)
- [Skype for Business と共存する](coexistence-chat-calls-presence.md)
-  [実装の詳細について共存とアップグレードの設定](https://aka.ms/SkypeToTeams-SetCoexistence) を設定します。

## <a name="related-links"></a>関連リンク

[ビデオ: SfB と Teams 間の共存と相互運用性を管理する](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
