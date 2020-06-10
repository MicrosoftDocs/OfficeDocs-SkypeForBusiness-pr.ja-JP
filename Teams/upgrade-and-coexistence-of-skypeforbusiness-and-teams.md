---
title: Skype for Business から Microsoft Teams へのアップグレード| モード、共存
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: Skype for Business と Microsoft Teams の共存オプションおよびモードの詳細と、いくつかのシナリオ例での Skype for Business から Teams へのアップグレード手順。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcb1570a87740d899a5f92957c0335e70d7f91ba
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665419"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Skype for Business から Teams へのアップグレード手順を選択する

![プロジェクトの定義ステージが強調表示されたアップグレード行程図](media/upgrade-banner-project-definition.png "「プロジェクトの定義」段階が強調表示された、アップグレード行程の各段階")

この記事は、お客様のアップグレード行程の「プロジェクトの定義」段階の一部です。 続行する前に、次の作業が完了していることを確認します。

- [プロジェクトの関係者をリスト化した](upgrade-enlist-stakeholders.md)
- [プロジェクトの対象範囲を定義した](https://aka.ms/SkypetoTeams-Scope)
- [Skype for Business と Teams の共存と相互運用を理解した](https://aka.ms/SkypeToTeams-Coexist)

既存の Skype for Business ユーザーである場合、Teams への完全な移行には時間がかかることがあります。 ただし、今すぐ Teams を Skype for Business と共存する形で有効にすることによって、関係するユーザーが Teams の価値を実感し始められるようになります。 2つのアプリ間に重複する機能がある場合は、使用可能な共存とアップグレードモードを確認して、どのパスが適切かを判断することをお勧めします。 たとえば、すべてのワークロードを、相互運用性のない状態で、両方のソリューションで有効にすることを選ぶことが考えられます。 または、お客様の組織において、すべてのユーザーを Teams にアップグレードさせられる準備が整うまで、段階的に Teams の機能を導入したり、一部の機能を使用できるユーザーのグループを絞り込んだりして、ユーザー エクスペリエンスを管理することを決めることも考えられます。 組織のために適切なアップグレード手順を評価するために、パイロットの結果を使用します。

> [!IMPORTANT]
> Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。それ以降、アクセスとサポートが終了します。 移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。

この記事では、Skype for Business および Teams のどのモダリティをユーザーが利用できるようにするかを管理できるようになる、さまざまなモードの概要を示します。 どのような展開においても、お客様の組織で Teams へのアップグレードを行う前に、選択したユーザー グループで、[対象の計画をパイロットする](pilot-essentials.md)ことを強くお勧めします。 新しいテクノロジーを導入することは、ユーザーにとって混乱をきたす可能性があるものであることを忘れないでください。 ここで概説されているいずれかのモードを実施する前に、ユーザーの準備状況を評価して、コミュニケーションおよびトレーニングの計画を実行するために時間を割きます。

> [!TIP]
> お客様は、指導、ベストプラクティス、およびアップグレードを開始するために設計されたリソースを共有するライブのインタラクティブなワークショップをお申し込みください。
>
>アップグレードを開始するには、最初に「[アップグレードの計画](https://aka.ms/SkypeToTeamsPlanning)」セッションにご参加ください。


## <a name="upgrade-journey-building-blocks"></a>アップグレード手順の構成単位

お客様の組織を Teams に移行するために正式に準備するためには、最終的に組織が Teams を唯一のコミュニケーションとコラボレーションのソリューションとして完全に受け入れられるようになるアップグレード シナリオ計画を開始する必要があります。

Skype for Business から Teams へのアップグレードに関連した、さまざまなモードや、コンセプトや、用語についての知識を深めることは、意思決定プロセスのガイドとして役に立ちます。 詳細については、「 [Microsoft Teams と Skype For business の共存と相互運用性](https://aka.ms/SkypeToTeams-Coexist)」を参照してください。

Teams に移行されたユーザーは、Skype for Business で開催される会議に参加する目的以外には Skype for Business クライアントを使用しません。 送信者が Teams または Skype for Business を使用しているかどうかに関係なく、ユーザーのチームクライアントですべての着信チャットと通話ができます。 アップグレード済みのユーザーによって開催される新しい会議は、Teams 会議としてスケジュールされます。 ユーザーが Skype for Business クライアントを使用しようとすると、チャットと通話の開始がブロックされます。<sup>1</sup> ただし、招待された会議に参加するには、ユーザーは Skype for Business クライアントを引き続き使用できます (使用する必要があります)。

管理者は、[TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) のプロパティである「[モード](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes)」という概念を使用して Teams への移行を管理します。 上で説明したように、Teams に移行されたユーザーは、"TeamsOnly" モードになります。 Teams に移行する組織の最終的な目標は、すべてのユーザーを TeamsOnly モードに移行することです。

Skype for Business を使用する既存の組織を Teams に移行するには、次の 2 つの方式があります。

- **重複機能方式** (アイランド モードを使用): 既存の Skype for Business 組織のユーザーが Teams に追加されることにより、これらのユーザーは移行期間中に両方のクライアントを併用できます。 この期間中、これらのユーザーは Teams のほとんどの機能 (全部ではありません) を利用できます。 この構成のモードは、"アイランド" と呼ばれ、これは Skype for Business を使用する既存の組織の既定のモードです。 組織での準備が整ったら、管理者はユーザーを TeamsOnly モードに移行します。

- **選択的機能方式** (Skype for Business の 1つまたは複数のモードを使用): 管理者は、組織内のユーザーのためにチャット、通話、会議スケジュール機能の Skype for Business から Teams への移行を管理します。 これらの機能はいずれも、Skype for Business または Teams のいずれかで使用できますが、両方で使用することはできません。 管理者は、ユーザーのためにこの機能を Teams に移行するタイミングを制御するのに TeamsUpgradePolicy を使用します。 まだ TeamsOnly モードになっていないユーザーは、引き続き Skype for Business を使用してチャットと通話を行います。2 つのグループのユーザーは、相互運用機能を使用して通信できます。 管理者は、段階的により多くのユーザーを Teams に移行させることにより、移行を管理します。

<sup>1</sup> 2017 前に出荷された古い Skype for business クライアントは、TeamsUpgradePolicy を認めません。 Office チャネルで入手できる、最新の Skype for Business クライアントを必ず使用してください。

以下は、組織にとって適切な移行行程を決定する上で役に立つ要素です。 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>重複機能方式 (アイランド モードを使用)

重複機能方式の場合、チャット、VoIP 通話、および会議を行うために、ユーザーは Teams と Skype for Business クライアントの両方を使用できます。 この方式では、Teams でのチャットと VoIP 通話は組織内専用であるのに対し、Skype for Business では外部組織とのチャットや VoIP/PSTN (公衆交換電話網) 通話が可能です (構成されている場合)。 会議のスケジュールと出席は、両方の製品で行えます。

重複機能方式を使用する場合、Skype for Business と Teams の通信トラフィックは (たとえ同一ユーザーのものであっても) 別々に保たれ、2 つの異なるクライアント同士が通信することはありません (同じ組織内のユーザーの場合)。 ユーザーエクスペリエンスは、受信者の構成に基づいています。 たとえば、受信者ユーザー A はこのアップグレード方式を使用しているとします。

- 別のユーザーの Skype for business クライアントから開始された通信は、ユーザー A の Skype for business クライアントに常に着陸します。

- *同じ組織内のユーザー*から開始されたチームクライアントからのコミュニケーションは、常にユーザー a のチームクライアントに着陸します。

- *外部組織のユーザー*から開始されたチームクライアントからの通信は、常にユーザー a の Skype for business クライアントに着陸します。

ユーザーに Microsoft 365 または Office 365 のライセンスを割り当てている場合、これが組織の既定のアップグレード環境となります。 Microsoft 365 または Office 365 のライセンスを割り当てると、Teams と Skype for Business Online ライセンスの両方が既定で割り当てられます。<sup>2</sup>

この方式を効果的に動作させるには、すべてのユーザーが両方のクライアントを同時に実行している必要があります。 組織内から受信するアイランド モードのユーザー宛てのチャットと通話は、Skype for Business クライアントと Teams クライアントのいずれにも配信される可能性があり、受信者はこれを制御できません。 これは、送信者が通信を開始するために使用するクライアントにより左右されます。 送信者と受信者の組織が異なる場合、アイランド モードのユーザー宛ての受信チャットと通話は、常に Skype for Business クライアントに配信されます。

たとえば、アイランド モードの受信者が Skype for Business にサインインし、Teams にはサインインしていない場合、メッセージはアイランド モードの受信者に表示されません (ただし、受信者が Teams でメッセージを受け取ることができなかったことを伝えるメールが後から受信者に送信されます)。 同様に、ユーザーが Skype for Business を実行し、Teams を実行していない場合、他のユーザーが Skype for Business からそのユーザー宛てにメッセージを送信すると、チャットはそのユーザーに表示されません。 これらのシナリオでの動作は、通話の場合も同様です。 ユーザーがいずれのクライアントも実行していない場合は、通信できません。

このアップグレード方式を使用する場合、プレゼンスは Teams と Skype for Business で独立して機能します。 そのため、ユーザー A のプレゼンス状態が他のユーザーに表示される際は、使用するクライアントによって、異なる状態が表示される可能性あります。 詳細については、「[プレゼンス](upgrade-to-Teams-on-prem-overview.md#presence)」を参照してください。

- 他のユーザーが Teams を使用すると、Teams でのユーザーのアクティビティに基づいてプレゼンスが表示されます。

- Skype for Business を使用している場合、他のユーザーには、Skype for Business でのユーザーのアクティビティに基づいてプレゼンスが表示されます。

ユーザーを TeamsOnly モードにアップグレードする準備ができたら、ユーザーを個別にアップグレードすることも、テナント全体のポリシーを使用してテナント全体を一度にアップグレードすることもできます。<sup>3</sup> ユーザーが TeamsOnly モードにアップグレードされると、ユーザーはすべての受信チャットと通話を Teams で受け取ります。

ただし、アイランド モードに設定されているアップグレード済みでない受信者の場合、TeamsOnly ユーザーからのチャットと通話は、引き続き Skype for Business クライアントまたは Teams クライアントのいずれでも受信できます。 既存の会話の場合、TeamsOnly ユーザーは、送信者がチャットまたは通話を開始する際に使用したクライアントに返信します。 

TeamsOnly ユーザーの視点からの新しい会話の場合、チャットまたは通話は常に、島々モードのユーザーチームクライアントに移動します。 これは、Teams クライアントでは、「Teams から Teams」の通信と「Teams から Skype for Business」の通信について、たとえ同一のユーザーのものであっても、個別の会話スレッドが維持されることによります。 詳細については、「[Teams の会話 - 相互運用とネイティブ スレッドの違い](upgrade-to-Teams-on-prem-overview.md#teams-conversations---interop-versus-native-threads)」を参照してください。

次の表は、アイランド モードと TeamsOnly モードの両方について Teams エクスペリエンスをまとめたものです。

| Teams エクスペリエンス | アイランド モードの場合 | TeamsOnly モードの場合 |
|:------------------ | :------------------- | :------------------ |
| 受信チャットと通話の配信先:|  Teams または Skype for Business | Teams |
| PSTN 通話の配信先: | Skype for Business <br>(Teams での PSTN 機能の使用は、アイランド モードではサポートされていません。)     | Teams |   
 |プレゼンス    | Skype for Business と Teams のプレゼンスは独立しています。 同一のアイランド ユーザーの状態が他のユーザーに表示される際は、使用するクライアントによって、異なる状態が表示される可能性あります。 | プレゼンスは、Teams でのユーザーのアクティビティにのみ基づいています。 他のすべてのユーザーには、使用するクライアントに関係なく、そのプレゼンスが表示されます。 | 
 | 会議のスケジュール    | ユーザーは、Teams または Skype for Business のいずれでも会議をスケジュールできます。 既定では、Outlook に両方のアドインが表示されます。 Teams 会議ポリシーを設定して、ユーザーが Teams 会議アドインのみを使用できるか、Teams 会議と Skype for Business の両方の会議アドインのどちらを使用するかを制御することができます。詳細については、「[島々 (孤島) モードでユーザーの会議プロバイダーを設定](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)する」を参照してください。 |     会議のスケジュールは、Teams のみで行います。 Outlook では、Teams アドインのみを使用できます。 | 

次の表は、組織を Teams へ移行させるために重複機能方式を使用する場合のメリットとデメリットをまとめたものです。

| メリット     |       デメリット |
| :------------------ | :---------------- |
| 組織内での迅速な導入が可能になります。| この 2 つのクライアントの機能は似通っている一方、ユーザー インターフェイスが異なるため、エンド ユーザーが混乱する可能性があります。 また、着信したチャットや通話の配信先クライアントをユーザーは制御できません。 |
| Skype for Business へアクセスを 100% 維持しつつ、Teams の学習と理解を深めることができます。 | ユーザーが両方のクライアントを実行していない場合はユーザーにメッセージが表示されないため、エンド ユーザーが不満に感じる可能性があります。|
| 最小限の管理作業で Teams の使用を開始できます。 | "孤島" モードを使用して、ユーザーと、そのユーザーが定期的に通信しているユーザーが Teams を積極的に使用していない場合は、[チーム] モードに移動することが難しい場合があります。|
|ユーザーは、Skype for Business では利用できない機能を活用することでチームワークを強化できるようになります。| Skype for Business オンプレミスおよび Teams を使用しているユーザーは、Skype for Business オンプレミスは使用しているが Teams は使用していない別のユーザーとは、Teams からでは通信できません。  |

<sup>2</sup>これは、ユーザーが Skype For business Server でオンプレミスになっている場合でも同様です。 ユーザーの所属がオンプレミスとオンラインのいずれであっても、Teams の機能をすべて使用するには Skype for Business Online が現状では必要なため、Skype for Business Online のライセンスを有効にしたままにします。

<sup>3</sup> Skype for business 会議から Teams の会議への移行は、テナントごとではなく、個々のユーザーに TeamsUpgradePolicy を適用した場合にのみトリガーされます。 詳細については、「[会議の移行](upgrade-to-Teams-on-prem-overview.md#meeting-migration)」を参照してください。

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>選択的機能方式 (Skype for Business の各モードを使用)

一部の組織では、組織を Skype for Business から Teams に移行する際に、予測がより容易なエクスペリエンスをエンド ユーザーに提供することを優先する場合があります。 このモデルでは、IT 管理者は TeamsUpgradePolicy 内の Skype for Business モードのいずれかを使用して、Teams への移行の前に Skype for Business に残す機能を明示的に指定します。 管理者は、選択した機能を TeamsOnly モードに移す準備ができたら、これらのユーザーのモードを TeamsOnly に更新します。 この移行中の動作は次のようになります。

- 管理者には、ユーザーを TeamsOnly エクスペリエンスに移す前に、チャットと通話の機能を Skype for Business に残したまま、ユーザーに対して特定の Teams 機能を有効にするオプションがあります。 管理者は、Teams の共同作業機能または Teams の会議/共同作業機能を有効にできます。

- Skype for Business を使っているユーザーは、他のユーザーのチームまたは Skype for Business クライアントからの通信が発生したかどうかに関係なく、Skype for business クライアントですべての着信チャットと通話を受け取ることができます。 また、これらの Skype for Business ユーザーに対しては、ユーザーの混乱を防ぎ、適切なルーティングとプレゼンスを確保するために、Teams クライアントでの通話とチャットの機能は無効になっています。

- 通信の発信元が Teams, Skype for Business、またはいかなる種類のフェデレーション ユーザーであった場合も、TeamsOnly モードのユーザーはすべての受信チャットと通話は Teams クライアントで受け取り、プレゼンスは Teams により提供されます。

重複機能方式とは異なり、選択的機能方式では、Skype for Business を使用しているユーザーは、TeamsOnly のユーザーと通信できます。 Skype for Business ユーザーと Teams ユーザーの間の通信は、[相互運用性](upgrade-to-Teams-on-prem-overview.md#interoperability)または "相互運用" と呼ばれます。 相互運用通信は、Skype for Business ユーザーと Teams の別のユーザーとの間の 1 対 1 ベースのチャットと通話で利用できます。 また、招待されたユーザーはいつでも Skype for Business 会議または Teams 会議に参加できますが、会議の種類に対応するクライアントを使用する必要があります。 詳細については、「[会議](upgrade-to-Teams-on-prem-overview.md#meetings)」を参照してください。

選択的機能方式のユーザーの場合、ユーザーのプレゼンスは、他のユーザーが使用するクライアントに関係なく、一定です。 ユーザーが Skype for Business モードのいずれかである場合、その他のすべてのユーザーには、Skype for Business でそのユーザーのアクティビティに基づいてプレゼンスが表示されます。 同様に、ユーザーが Teams の唯一のモードにある場合、他のすべてのユーザーには、そのユーザーのチームのアクティビティに基づいてプレゼンスが表示されます。 詳細については、「[プレゼンス](upgrade-to-Teams-on-prem-overview.md#presence)」を参照してください。

選択的機能方法を採用する組織の場合、管理者は、テナント全体のモードを、アイランドから適切な Skype for Business 共存モード (SfbWithTeamsCollab または SfBWithTeamsCollabAndMeetings) に変更する必要があります。  

ゲスト ユーザーのエクスペリエンスは、テナントに割り当てられている共存モードに従います。 Skype for Business モードをテナント レベルで設定した場合、ゲストはチャット、通話、またはプレゼンスの表示を行うことができません。 詳細については、「[Teams でのゲスト アクセス](guest-access.md)」を参照してください。

モードがアイランドから SfbWithTeamsCollab に変わった場合、Teams をまだ一度も使用したことがないユーザーの場合は、Skype for Business の使い方は変わりません。 しかし、そのユーザーが Teams の使用を開始した場合、チームとチャネルやファイルなどの機能のみを利用できます。 チャット、通話、会議のスケジュールは、優先クライアントとして Skype for Business が管理者により (現在は) 指定されているため、Teams では利用できません。

> [!NOTE]
> ユーザーが孤島から Skype for Business モードのいずれかに変更した場合、ユーザー a と通信する他のユーザーのチームクライアントは、ユーザー A の適切なクライアントに通信をルーティングできるように、ユーザー a のモードが変更されたことを知る必要があります。ユーザー A とのネイティブのチーム間チャットを既に確立しているユーザーについては、他のユーザーのチームクライアントが、島から任意の Skype for Business モードへのモードの変更を認識できるように、時間がかかることがあります。 管理者は、ユーザーのモードを Teams に更新することで、特定のユーザーのチャット、通話、会議のスケジュール設定を一度に1つずつ行うことができます。

別の方法として、SfBWithTeamsCollabAndMeetings モードを使用することで、管理者はチャットと通話機能を Skype for Business に残したまま、まずは会議のスケジュールのみを Teams に移すことができます。 このモードでは、組織は会議のためにチームに切り替えることができます。ユーザーがまだ TeamsOnly モードに移行する準備ができていない場合 (たとえば、既存の PSTN 機能を移行する準備がまだできていない場合など)。 この移行シナリオは、[Meetings First (最初に会議)](meetings-first.md) と呼ばれます。


|Teams エクスペリエンス  |SfBWithTeamsCollab モードの場合 |SfBWithTeamsCollabAndMeetings モードの場合 |TeamsOnly モードの場合  |
|---------|---------|---------|---------|
|組織内のユーザーからの受信チャットと VoIP 通話の配信先:     | Skype for Business        | Skype for Business       | Teams        |
|PSTN 通話の配信先:     | Skype for Business        |Skype for Business         | Teams        |
|プレゼンス     | Skype for Business        |Skype for Business         | Teams        |
|会議のスケジュール     | Skype for Business         | Teams        | Teams        |


次の表は、TeamsOnly モードへの移行段階として Skype for Business モードを使用する場合のメリットとデメリットをまとめたものです。

| メリット     |       デメリット |
| :------------------ | :---------------- |
| エンド ユーザーにとって予測可能なルーティングです。 すべての通話とチャットは、管理者の選択に基づき、Skype for Business または Teams のいずれかに配信されます。|相互運用会話では、リッチ テキスト、ファイル共有、画面共有はサポートされていません。 回避策として、[今すぐ会議] 機能を使用して会議を開始するという方法があります。 |
|各機能は 1 つのクライアントでのみ使用可能であるため、エンド ユーザーの混乱を軽減できる可能性があります。 | ユーザーは、Skype for Business で実行された一般的なアクティビティ (たとえば、チャットや Teams へのアップグレードの前) でのチームへのアクセス権を持ちません。|
|Skype for Business から Teams への移行中、ユーザーが利用できる機能のセットに関する管理者の制御能力が高まります。 | |
| 組織を TeamsOnly モードへ完全に移行する準備ができていない場合でも、組織は会議のために Teams を使用できます。||
|他のユーザーに表示される特定のユーザーのプレゼンスは、使用するクライアントに関係なく同じです。||

## <a name="summary-of-upgrade-methods"></a>アップグレード方式のまとめ
次の表は、各アップグレード方式についてのまとめです。


|重複機能 (アイランド モードを使用)  |選択的機能 (Skype for Business の各モードを使用)  |
|---------|---------|
|受信チャットと通話はいずれのクライアントにも配信される可能性があるため、TeamsOnly にアップグレードされる前に、ユーザーは両方のクライアントを同時に実行する必要があります。     | チャットと通話は、受信者のモードに基づいて1つのクライアントにのみ対応しています。 アップグレード済みではないユーザーは両方のクライアントを実行することができますが、機能の重複はありません (通話とチャットは Teams では利用できません)。         |
|管理者は、重複機能 (チャット、会議、VoIP 通話) および Teams の新機能 (チームとチャネル) を Skype for Business と Teams の両方でエンド ユーザーに提供できます。     | 管理者は、Skype for Business にも備わっているものと同じ機能を提供することなく、Teams の機能 (チームとチャネル) を選択的にエンド ユーザーに提供できます。        |
|両方のユーザーがアイランド モードである間は、Skype for Business と Teams との間に相互運用性は生まれません。      |Skype for Business ユーザーと Teams ユーザーの間のコミュニケーションには、相互運用性が必要です。         |

> [!NOTE]
> サポートされている、Skype for Business Server ユーザーを Teams に移行するための方式に従うことが難しい場合は、Skype for Business サーバーと Active Directory にある関連するすべてのユーザー属性を削除することで、ユーザーを Teams に移行することが可能です。 ユーザーの Azure Active Directory 属性が Skype for Business Server の属性によって消去され、DNS レコードが Microsoft 365 または Office 365 を参照していると、Microsoft 365 または Office 365 でユーザーをライセンスして、それらのユーザーを Teams にアップグレードすることができます。 

> [!IMPORTANT]
> 一括移行では、連絡先データと会議データはオンプレミス環境から Microsoft Teams に移行されません。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>判断ポイント</td><td><ul> どのアップグレード手順が組織のビジネス要件に適してますか?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>次の手順</td><td><ul> 現在の展開モデル、ユースケースシナリオ、および組織にとって最適なチームへの旅を組織が把握するための重要な考慮事項を特定します。<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>判断ポイント</td><td><ul> お客様の組織に該当するアップグレード シナリオはどれですか?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>次の手順</td><td><ul> メッセージング、会議、および通話のビジネス要件に基づいて、お客様の組織のアップグレード手順のタイムラインを決定します。<br><br> アップグレード手順を完了するために必要な追加作業を決めます。<br><br></ul></td></tr>
</table>

組織に最適なアップグレードを選択した後、[チームへのアップグレードを実行](https://aka.ms/SkypeToTeams-Upgrade)します。
