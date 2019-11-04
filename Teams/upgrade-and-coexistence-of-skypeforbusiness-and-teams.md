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
ms.openlocfilehash: 5de243402cd5694b2e4a498f7ff7650cd8f49f4a
ms.sourcegitcommit: 2e005b335b1566c99b93fc311498702838466324
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "37931645"
---
![プロジェクト定義ステージを強調したアップグレードの図](media/upgrade-banner-project-definition.png "プロジェクト定義ステージに重点を置いたアップグレードの段階")

この記事は、アップグレード過程のプロジェクト定義の段階に含まれています。 先に進む前に、次のアクティビティを完了していることを確認してください。

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

チームに移行されたユーザーが、skype for business クライアントを使用しなくなりました。ただし、Skype for Business でホストされている会議に参加することはありません。 送信者が Teams または Skype for Business を使用しているかどうかに関係なく、ユーザーのチームクライアントですべての着信チャットと通話ができます。 アップグレードしたユーザーによって開催された新しい会議は、Teams の会議としてスケジュールされます。 ユーザーが Skype for Business クライアントを使用しようとすると、チャットの開始と通話<sup>はブロックされます</sup>。 ただし、ユーザーは引き続き Skype for Business クライアントを使用して、招待された会議に参加することができます。

管理者は、 [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)のプロパティである[モード](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes)の概念を使って、チームへの切り替えを管理します。 上で説明したように、Teams に移行されたユーザーは、"TeamsOnly" モードになります。 チームに移行する組織の場合、最終的な目標は、すべてのユーザーを Teams Sonly モードに移行することです。

既存の組織を Skype for Business (オンラインまたはオンプレミス) のチームに移行するには、次の2つの方法があります。

- **機能のオーバーラップ方法**(孤島モードを使用): 既存の Skype for business 組織のユーザーは、移行フェーズで両方のクライアントを並べて使用できるように、Teams に導入されています。 この期間中は、チームのすべての機能ではなく、ほとんどすべての機能を利用できます。 この構成のモードは、"孤島" と呼ばれます。これは、Skype for Business を使用する既存の組織の既定のモードです。 組織の準備ができたら、管理者はユーザーを teams Sonly モードに移行します。
- **[機能の方法]** (1 つ以上の Skype for business モードを使用) を選択します。管理者は、組織内のユーザーのために、チャット、通話、および会議のスケジュール機能の移行 (Skype for Business から Teams への切り替え) を管理します。 これらの関数は、いずれも Skype for Business または Teams で利用できますが、両方を使用することはできません。 管理者は、TeamsUpgradePolicy を使用して、この機能をユーザーのチームに移行するタイミングを制御します。 まだ TeamsOnly モードになっていないユーザーは、引き続き Skype for Business を使用してチャットや通話を行うことができます。また、2つのユーザーを相互運用機能で通信することができます。 管理者は、より多くのユーザーを TeamsOnly モードに段階的に移行することで、切り替えを管理します。

<sup>1</sup>2017より前に出荷された古い Skype for Business クライアントは、TeamsUpgradePolicy を認めません。 Office のチャネルで利用できる最新の Skype for Business クライアントを使用していることを確認します。

以下は、組織に適したパスを決定するための主要な要因です。 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>重複する機能の方法 (孤島モードを使用)

機能のオーバーラップ方法では、ユーザーはチームと Skype for Business クライアントの両方を使用してチャット、VoIP 通話、会議を行うことができます。 この方法では、Teams のチャットおよび VOIP 通話は組織内で重点的に処理されますが、Skype for Business では、外部組織とのチャットや VOIP/PSTN 通話を有効にすることができます (構成されている場合)。 両方の製品で会議をスケジュールし、出席することができます。

重複機能の方法を使用する場合、Skype for Business と Teams の通信トラフィックは、(同じユーザーに対しても) 別々に維持され、2つの異なるクライアントは相互に通信できません (同じ組織内のユーザーの場合)。 ユーザーエクスペリエンスは、受信者の構成に基づいています。 たとえば、受信者のユーザー A がこのアップグレード方法を使用しているとします。

- 別のユーザーの Skype for business クライアントから開始された通信は、ユーザー A の Skype for business クライアントに常に着陸します。
- *同じ組織内のユーザー*から開始されたチームクライアントからのコミュニケーションは、常にユーザー a のチームクライアントに着陸します。
- *外部組織のユーザー*から開始されたチームクライアントからの通信は、常にユーザー a の Skype for business クライアントに着陸します。

ユーザーに Office 365 ライセンスが割り当てられている場合、これは組織の既定のアップグレード環境となります。 Office 365 ライセンスを割り当てると、Teams と Skype for Business Online ライセンスの両方が既定で割り当てられます。<sup>2</sup>

この方法で効率的に作業するには、すべてのユーザーが両方のクライアントを同時に実行する必要があります。 組織内のユーザーとの間でのチャットや通話の着信は、Skype for Business または Teams クライアントのどちらかに着陸できます。これは、受信者の管理下にありません。 これは、送信者が通信を開始するために使用するクライアントによって異なります。 送信者と受信者が異なる組織にある場合は、諸島モードでのユーザーへの通話とチャットの着信が常に Skype for Business クライアントに着陸します。

たとえば、孤島モードの受信者が Skype for Business にサインインしていて、Teams からメッセージを送信している場合、その他のユーザーが Teams からメッセージを送信しても、諸島モードの受信者にはメッセージが表示されません (最終的には、Teams でメッセージが表示されなくなったことを示すメールが届きます) 同様に、ユーザーがチームを実行していても、Skype for business を使っていない場合、そのユーザーが Skype for Business からのメッセージを受け取った場合、そのチャットは表示されません。 各ケースの動作は、通話の場合と似ています。 ユーザーが両方のクライアントを実行しない場合は、簡単に不満を招く可能性があります。

プレゼンスは、このアップグレード方法を使用して、Teams と Skype for Business で個別に機能します。 これにより、他のユーザーは、使用しているクライアントに応じて、ユーザー A に異なるプレゼンス状態が表示されることがあります。 詳細については、「[プレゼンス](upgrade-to-Teams-on-prem-overview.md#presence)」を参照してください。

- 他のユーザーが Teams を使用すると、Teams でのユーザーのアクティビティに基づいてプレゼンスが表示されます。
- Skype for Business を使用している場合、他のユーザーには、Skype for Business でのユーザーのアクティビティに基づいてプレゼンスが表示されます。

ユーザーを TeamsOnly モードにアップグレードする準備ができたら、ユーザーを個別にアップグレードするか、テナント全体のポリシー<sup>3</sup>を使用してテナント全体を一度にアップグレードできます。 ユーザーが TeamsOnly モードにアップグレードされると、チーム内のすべての着信チャットと通話が受信されます。

ただし、島々モードでアップグレードされていない受信者は、Skype for Business または Teams クライアントで、TeamsOnly ユーザーからのチャットや通話を引き続き受信する可能性があります。 既存の会話の場合、TeamsOnly ユーザーは、送信者がチャットまたは通話を開始したクライアントに返信します。 

TeamsOnly ユーザーの視点からの新しい会話の場合、チャットまたは通話は常に、島々モードのユーザーチームクライアントに移動します。 これは、チームのクライアントが、同じユーザーに対してもチーム間とチーム間の通信スレッドの個別の会話スレッドを保持しているためです。 詳細については、「[チームの会話-相互運用とネイティブスレッドの比較](upgrade-to-Teams-on-prem-overview.md#teams-conversations---interop-versus-native-threads)」を参照してください。

次の表は、島々モードと TeamsOnly モードの両方の Teams エクスペリエンスをまとめたものです。

| Teams のエクスペリエンス | 諸島モードの場合 | TeamsOnly モードの場合 |
|:------------------ | :------------------- | :------------------ |
| 受信したチャットと通話:|  Teams または Skype for Business | Teams |
| 受信した PSTN 通話: | Skype for Business <br>(Teams での PSTN 機能の使用は、諸島モードではサポートされていません)。    | Teams |   
 |プレゼンス  | Skype for Business および Teams のプレゼンスは、独立しています。 ユーザーが使用しているクライアントによって、同じ島々ユーザーに対して異なる状態が表示されることがあります。 | プレゼンスは、Teams でのユーザーのアクティビティにのみ基づいています。 他のすべてのユーザー (使用しているクライアントに関係なく) は、そのプレゼンスを確認してください。 | 
 | 会議のスケジュール   | ユーザーは、チームまたは Skype for Business で会議をスケジュールできます。 Outlook で両方のアドインが表示されます。 |   ユーザーは Teams でのみ会議をスケジュールします。 Teams アドインのみが Outlook で利用できます。 | 

次の表は、重複する機能を使用して組織を Teams に移行する場合の長所と短所をまとめたものです。

| 担当     |       面 |
| :------------------ | :---------------- |
| 組織内での迅速な導入を可能にします。| 類似した機能を持つ2つのクライアントがあり、ユーザーインターフェイスが異なるため、エンドユーザーが混乱する可能性があります。 また、通話の発信先のクライアントを管理することもできません。 |
| ユーザーは、Skype for Business へのフルアクセスを保持しながら、チームについて学習し、理解を深めることができます。 | ユーザーが両方のクライアントを実行していない場合に、メッセージが見つからないという理由でエンドユーザーの不満が発生する可能性があります。|
| チームで作業を開始するための最小限の管理作業。 | "孤島" モードを使用して、ユーザーと、そのユーザーが定期的に通信しているユーザーが Teams を積極的に使用していない場合は、[チーム] モードに移動することが難しい場合があります。|
|ユーザーが機能を活用して、Skype for Business で利用できないチームワークを強化できるようにします。| オンプレミスの Skype for Business を使用しているユーザーは、社内の Skype for Business を使用しているが、teams を持っていない他のユーザーとの通信を行うことはできません。  |

<sup>2</sup>これは、ユーザーが Skype for Business Server でオンプレミスになっている場合でも同様です。 ユーザーがオンプレミスまたはオンラインのどちらであるかにかかわらず、Skype for Business Online ライセンスが有効になったままにしておきます。現在のところ、Teams のすべての機能が必要であるためです。

<sup>3</sup>Skype for Business 会議から Teams の会議への移行は、個々のユーザーに TeamsUpgradePolicy を適用した場合にのみトリガーされ、テナントごとには表示されません。 詳細については、「[会議の移行](upgrade-to-Teams-on-prem-overview.md#meeting-migration)」をご覧ください。

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Select capabilities メソッド (Skype for Business モードを使用)

組織によっては、Skype for Business から Teams への移行により、エンドユーザーにより予測可能なエクスペリエンスを提供することがあります。 このモデルでは、IT 管理者は、TeamsUpgradePolicy で Skype for Business モードの1つを使用して、teams Sonly モードに移行する前に、Skype for Business に残る機能を明示的に指定します。 選択した機能を teams Sonly モードに移行する準備ができたら、管理者は、ユーザーのモードを [チーム] のみに更新します。 切り替え中:

- 管理者には、ユーザーに対して特定のチーム機能を有効にするオプションがあります。ユーザーは、Skype for Business のチャットや通話機能を維持したままで、ユーザーが Teams のエクスペリエンスのみに移行できます。 管理では、チームのコラボレーション機能または Teams 会議とコラボレーション機能を有効にすることができます。
- Skype for Business を使っているユーザーは、他のユーザーのチームまたは Skype for Business クライアントからの通信が発生したかどうかに関係なく、Skype for business クライアントですべての着信チャットと通話を受け取ることができます。 また、これらの Skype for Business ユーザーの場合、Teams クライアントでの通話とチャット機能は無効になるので、エンドユーザーの混乱を防ぎ、適切なルーティングとプレゼンスを確保することができます。
- チーム内のユーザーは、チーム、Skype for Business、またはどのようなフェデレーションユーザーからの通信が行われたかに関係なく、チームによって、すべての受信チャットと通話を、teams によって受信します。

重複機能の方法とは異なり、select 機能の方法では、Skype for Business を使用しているユーザーは、チームのユーザーと通信できます。 Skype for Business ユーザーと Teams ユーザーの間の通信は、[相互運用性](upgrade-to-Teams-on-prem-overview.md#interoperability)または "相互運用" と呼ばれます。 相互運用通信は、Skype for Business のユーザーと Teams 内の別のユーザーとの間でチャットや通話を行うために、1対1の通信として使用できます。 また、招待されたユーザーはいつでも Skype for Business 会議または Teams 会議に参加できます。ただし、会議の種類に対応したクライアントを使用する必要があります。 詳細については、「[会議](upgrade-to-Teams-on-prem-overview.md#meetings)」を参照してください。

Select capabilities メソッドのユーザーについては、他のユーザーがどのクライアントを使用しているかに関係なく、ユーザーのプレゼンスが一貫しています。 ユーザーが Skype for Business モードのいずれかである場合、その他のすべてのユーザーには、Skype for Business でそのユーザーのアクティビティに基づいてプレゼンスが表示されます。 同様に、ユーザーが Teams の唯一のモードにある場合、他のすべてのユーザーには、そのユーザーのチームのアクティビティに基づいてプレゼンスが表示されます。 詳細については、「[プレゼンス](upgrade-to-Teams-on-prem-overview.md#presence)」を参照してください。

Select 機能の使用を選択した組織の場合、管理者は、テナント全体モードを孤島から、適切な Skype for Business の共存モード (SfbwithteamsSfBWithTeamsCollabAndMeetings Ab または) に変更する必要があります。  

ゲストユーザーエクスペリエンスは、テナントに割り当てられている共存モードに従います。 Skype for Business モードをテナントレベルで設定した場合、ゲストはチャット、通話、またはプレゼンスの表示を行うことはできません。 詳細については、「[Teams でのゲスト アクセス](guest-access.md)」をご覧ください。

モードが島々から Sfbwithteamab に変更された場合、チームを使用していないユーザーには、Skype for Business の使用方法に違いはありません。 ただし、ユーザーが Teams の使用を開始する必要がある場合は、Teams & チャネル、ファイルなどの機能に対してのみ公開されます。 チャット、通話、会議のスケジュール設定は、Teams では使用できません。管理者は、これらの機能の目的のクライアントとして Skype for Business を指定したためです。

> [!NOTE]
> ユーザーが孤島から Skype for Business モードのいずれかに変更した場合、ユーザー a と通信する他のユーザーのチームクライアントは、ユーザー A の適切なクライアントに通信をルーティングできるように、ユーザー a のモードが変更されたことを知る必要があります。ユーザー A とのネイティブのチーム間チャットを既に確立しているユーザーについては、他のユーザーのチームクライアントが、島から任意の Skype for Business モードへのモードの変更を認識できるように、時間がかかることがあります。 管理者は、ユーザーのモードを Teams に更新することで、特定のユーザーのチャット、通話、会議のスケジュール設定を一度に1つずつ行うことができます。

または、最初に、SfBWithTeamsCollabAndMeetings モードを使用して Skype for Business のチャットや通話機能を残しながら、会議のスケジュールのみを Teams にシフトすることもできます。 このモードでは、組織が会議のためにチームに移行することができます。ユーザーがまだ TeamsOnly モードに移行する準備ができていない場合 (たとえば、既存の PSTN 機能を移行する準備ができていない場合)。 この移行シナリオは、[まず会議](meetings-first.md)として参照されます。


|Teams のエクスペリエンス  |Sfbwithteamsの [| |SfBWithTeamsCollabAndMeetings モードの場合 |TeamsOnly モードの場合  |
|---------|---------|---------|---------|
|組織内のユーザーからのチャットおよび VOIP 通話の受信:     | Skype for Business        | Skype for Business       | Teams        |
|受信した PSTN 通話:     | Skype for Business        |Skype for Business         | Teams        |
|プレゼンス     | Skype for Business        |Skype for Business         | Teams        |
|会議のスケジュール     | Skype for Business         | Teams        | Teams        |


次の表では、teams Sonly モードの移行手順として、Skype for Business モードを使用する場合の長所と短所をまとめています。

| 担当     |       面 |
| :------------------ | :---------------- |
| エンドユーザーに対して予測可能なルーティング。 Skype for Business または Teams (両方ではありませんが) で、すべての通話とチャットが管理者によって選択されています。|相互運用スレッドは、リッチテキスト、ファイル共有、画面共有には対応していません。 これは、会議を開始するための「今すぐミーティング」機能を活用することに関連しています。 |
|特定の機能が1つのクライアントでのみ利用可能であるため、エンドユーザーの混乱を軽減する可能性があります。 | ユーザーは、Skype for Business で実行された一般的なアクティビティ (チャット、Teams へのアップグレードの前) については、Teams へのアクセス権がありません。|
|管理者は、Skype for Business から Teams への移行中に、ユーザーが利用できる機能のセットを制御することができます。 | |
| チームが会議についてチームを使用できるようにします。チームは、完全に Teams のみに移行する準備がまだできていない場合でも、チームを使用できます。||
|他のユーザーによって表示されるユーザーのプレゼンスは、どのクライアントを使っているかにかかわらず同じです。||

## <a name="summary-of-upgrade-methods"></a>アップグレード方法の概要
次の表は、アップグレード方法をまとめたものです。


|機能のオーバーラップ (孤島モードを使用)  |選択された機能 (Skype for Business モードを使用)  |
|---------|---------|
|ユーザーは、teams にアップグレードする前に、チャットを開始してから両方のクライアントを同時に実行する必要があります。また、どちらのクライアントにも通話が表示されることがあります。     | チャットと通話は、受信者のモードに基づいて1つのクライアントにのみ対応しています。 アップグレードされていないユーザーは両方のクライアントを実行できますが、機能のオーバーラップはありません (通話とチャットは Teams では利用できません)。         |
|管理者が、Skype for Business と Teams の両方に、重なり合った機能 (チャット、会議、VOIP 通話) を、チームの新しい機能 (チームとチャネル) にも導入できるようにします。     | Skype for Business にも存在するのと同じ機能を提供することなく、管理者がチームの選択機能を利用できるようにします (チームとチャネル)。        |
|Skype for Business と Teams の間の相互運用性は、両方のユーザーが孤島モードになっている間は存在しません。      |Skype for Business と Teams ユーザーの間の通信には相互運用性が必要です。         |

> [!NOTE]
> Skype for business Server ユーザーをチームに移行するためにサポートされている方法を使用できない場合は、Skype for Business Server と Active Directory 内のすべての関連ユーザー属性を削除して、ユーザーをチームに移行することができます。 ユーザーの Azure Active Directory 属性が Skype for Business Server の属性によって消去され、DNS レコードが Office 365 を参照するようになると、Office 365 でユーザーをライセンスして、それらのユーザーを Teams にアップグレードすることができます。 

> [!IMPORTANT]
> カットオーバー移行では、連絡先データと会議データはオンプレミス環境から Microsoft Teams に移行されません。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>判断ポイント</td><td><ul> どのアップグレード手順が組織のビジネス要件に適してますか?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>次のステップ</td><td><ul> お客様の組織での現在の展開モデル、ユース ケースのシナリオ、および主な考慮事項を特定することにより、組織に最も適した Teams への移行手順がわかるようになります。<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>判断ポイント</td><td><ul> お客様の組織に該当するアップグレード シナリオはどれですか?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次のステップ</td><td><ul> メッセージング、会議、および通話のビジネス要件に基づいて、お客様の組織のアップグレード手順のタイムラインを決定します。<br><br> アップグレード手順を完了するために必要な追加作業を決めます。<br><br></ul></td></tr>
</table>

組織にとって最高のアップグレード手順を選んだ後、[Teams に対するアップグレードを実行します](https://aka.ms/SkypeToTeams-Upgrade)。
