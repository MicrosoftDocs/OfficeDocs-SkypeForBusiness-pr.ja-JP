---
title: Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Skype for Business から Teams への移行を管理するためのガイダンス
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.teamsupgrade.overview
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fe85942a943bcfb5a9645030924acd4180d250a
ms.sourcegitcommit: 7ca7f5cd38742b6a1967bd792113348dfe689850
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "30641344"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス

> [!Tip] 
> [共存および相互運用性の詳細については、こちらのセッション](https://aka.ms/teams-upgrade-coexistence-interop)をご覧ください。

Skype for Business を使用する組織が Teams を導入するとき、管理者は TeamsUpgradePolicy のプロパティである共存 "モード" の概念を使用して、組織のユーザー エクスペリエンスを管理することができます。 モードを使用すると、管理者は Skype for Business から Teams への切り替えを管理するときに、相互運用と移行を管理することができます。  ユーザーのモードによって、受信チャットと通話が届くクライアントと、新しい会議がスケジュールされるサービス (Teams または Skype for Business) が決定されます。 モードは今後、使用可能な機能に関して Teams クライアントの動作を定義するためにも使用されるようになります。 


## <a name="fundamental-concepts"></a>基礎概念

1.  *相互運用性* : Lync/Skype for Business ユーザーと Teams ユーザーの間の 1 対 1 の通信。

2.  *フェデレーション*: さまざまなテナントのユーザー間の通信。

3.  Teams ユーザーはすべて、オンラインまたはオンプレミスのいずれかに "所属" する、基本の Skype for Business アカウントを所有しています。
    - 既に Skype for Business Online を使用しているユーザーは、既存のオンライン アカウントを使用します。
    - 既にオンプレミスの Skype for Business/Lync を使用しているユーザーは、既存のオンプレミス アカウントを使用します。
    - 既存の Skype for Business アカウントが検出できないユーザーの場合、Teams ユーザーが作成されたときに、Skype for Business Online アカウントが自動的にプロビジョニングされます。

4.  Skype for Business または Lync いずれかのオンプレミス展開が存在し、そのユーザーを Teams のユーザーとする必要がある場合は、Teams/Skype for Business Online によりオンプレミス環境が適切に検出されるよう、少なくとも Azure AD Connect が msRTCSIP-DeploymentLocator を AAD に同期していることを確認する必要があります。 さらに、どのユーザーを TeamsOnly モードに移行する (つまりユーザーをアップグレードする) 場合でも、*まず Skype for Business ハイブリッド モードを構成する必要があります*。 詳細については、[Skype for Business と Teams 向けの Azure AD Connect の構成](https://docs.microsoft.com/ja-JP/SkypeForBusiness/hybrid/configure-azure-ad-connect)に関する記事を参照してください。

5.  Teams と Skype for Business ユーザー間の相互運用は、*Teams ユーザーが Skype for Business でオンラインに所属している場合のみ可能です*。 受信者となる Skype for Business ユーザーは、オンプレミス (Skype for Business ハイブリッドの構成が必要) またはオンラインに所属できます。 オンプレミスの Skype for Business に所属しているユーザーはアイランド モード (このドキュメントの後で定義されます) で Teams を使用できますが、Skype for Business を使用している他のユーザーとの相互運用またはフェデレーションのために Teams を使用することはできません。  

6.  アップグレードと相互運用の動作は、後で説明するユーザーの共存モードに基づいて決定されます。 モードは、TeamsUpgradePolicy によって管理されます。 TeamsInteropPolicy は優先されなくなり、granting mode=Legacy の付与も許可されなくなりました。 

7.  ユーザーを TeamsOnly モードにアップグレードすることにより、発信元のクライアントとは無関係に、すべての受信チャットと通話がユーザーの Teams クライアントに常に届くようになります。 また、アップグレードされたユーザーは新しい会議を Teams でスケジュールするようになります。 TeamsOnly モードにするには、ユーザーが Skype for Business でオンラインに所属している必要があります。 これは、Teams ユーザーの確実な相互運用、フェデレーション、完全な管理のために必要です。ユーザーを TeamsOnly にアップグレードするには、次の操作を実行します。
    - ユーザーが Skype for Business Online に所属している (または Skype アカウントを所有したことがない) 場合、PowerShell で "UpgradeToTeams" を使用して、Mode=TeamsOnly で TeamsUpgradePolicy をそのユーザーに付与します。または、Teams 管理センターを使用して TeamsOnly モードを選択します。
    - ユーザーがオンプレミスに所属している場合、オンプレミスの管理ツールから `Move-CsUser` を使用して、まずそのユーザーを Skype for Business Online に移動します。  Skype for Business Server 2019 または CU8 for Skype for Business Server 2015 をお持ちの場合、`Move-CsUser` で `-MoveToTeams` スイッチを指定して、オンラインへの移行の一環としてユーザーを直接 Teams に移動することができます。 このオプションでは、ユーザーの会議も Teams に移行されます (ただし、会議の移行が可能なのは現在、TAP のお客様のみです)。 `-MoveToTeams` が指定されていないか使用できない場合、`Move-CsUser` の完了後に PowerShell または Teams 管理センターを使用して、TeamsOnly モードをそのユーザーに割り当てます。 詳細については、「[ユーザーのオンプレミスとクラウド間の移動](https://docs.microsoft.com/ja-JP/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)」を参照してください。  会議の移行の詳細については、「[会議移行サービス (MMS) の使用](https://docs.microsoft.com/ja-JP/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。

8.  ユーザーが Teams 電話システムを Teams で使用するには、TeamsOnly モードである (つまり、Skype for Business Online に所属しており、Teams にアップグレードされている) 必要があります。また、Microsoft 電話システムの[ダイレクト ルーティング](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) (自分の SIP トランクと SBC で電話システムを使用するための機能) 向けに構成されているか、または Office 365 通話プランを利用している必要があります。   

9.  現在、電話会議 (PSTN 経由のダイヤルインまたはダイヤルアウト) を使用して Teams の会議をスケジュールすることは、Skype for Business Online に所属しているユーザーのみが可能です。 オンプレミスの Skype for Business アカウントを持つ Teams ユーザーに対するサポートは、TAP で行われます。


## <a name="coexistence-modes"></a>共存モード

相互運用と移行は、TeamsUpgradePolicy を使用する "共存モード" に基づいて管理されます。 共存モードは、組織が Skype for Business から Teams に移行するときに、シンプルで予測可能な操作環境をエンド ユーザーに提供します。 Teams に移行する組織にとって、各ユーザーの最終的な目的地は TeamsOnly モードですが、すべてのユーザーに TeamsOnly (またはその他のモード) を同時に割り当てる必要はありません。 ユーザーが TeamsOnly モードに到達する前に、組織は Skype for Business の任意のモード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) を使用して、TeamsOnly であるユーザーとまだ TeamsOnly ではないユーザー間の予測可能な通信を確保することができます。


技術的な観点からは、ユーザーのモードによってユーザーの操作環境のいくつかの側面が制御されます。

- *受信ルーティング*: 受信チャットと通話が、どのクライアント (Teams または Skype for Business) に届くのか。 
- *プレゼンス公開*: 他のユーザーに表示されるユーザーのプレゼンスが、Teams または Skype for Business のいずれのアクティビティに基づいたものなのか。 
- *会議のスケジュール*: 新しい会議のスケジュール、そして適切なアドインが Outlook に存在することを確認するのに使用されるサービスはどれなのか。 TeamsUpgradePolicy は会議への参加については制御しないことに注意してください。 ユーザーは常に、Skype for Business または Teams のいずれの会議であっても、*参加*することができます。
- *クライアント エクスペリエンス*: Teams または Skype for Business で利用可能な機能はどれなのか。 ユーザーは通話やチャットを、Teams または Skype for Business のいずれで開始できるのか、または両方で開始できるのか。 チームとチャンネルのエクスペリエンスは使用可能なのか。  この記事の後で説明しますが、このモードの最終的な側面の提供が開始されました。

モードに基づくルーティングとプレゼンスの動作の詳細については、「[Skype for Business との共存](https://docs.microsoft.com/ja-JP/MicrosoftTeams/coexistence-chat-calls-presence)」を参照してください。

一方で、エクスペリエンスの観点からは、モードは次のエクスぺリエンスを定義するものであると、よりシンプルに説明することができます。
- *チャットと通話*: ユーザーが使用するクライアントはどれなのか。
- *会議のスケジュール*: ユーザーは新しい会議を Teams と Skype for Business のいずれの会議としてスケジュールするのか。
- *Teams クライアントでの共同作業機能の使用可能性*。 ユーザーがまだ Skype for Business を所有している場合、チームとチャンネル、およびファイル機能を使用できるかどうか。

モードの一覧を次に示します。
</br>
</br>

|モード|通話とチャット|会議のスケジュール<sup>1</sup>|チームとチャンネル|使用例|
|---|---|---|---|---|
|**TeamsOnly**</br>*Skype for Business Online に所属していることが必要*|Teams|Teams|あり|アップグレード過程の最終的な状態。 シートが 500 未満の新しいテナントの既定値でもあります。|
|アイランド|いずれか|いずれか|あり|既定の構成。 1 人のユーザーが両方のクライアントを並べて比較することができます。 チャットと通話はいずれかのクライアントに届くので、ユーザーは両方のクライアントを常に起動しておく必要があります。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|あり|"会議優先"。 主に、通話のクラウドへの移行準備ができていないオンプレミスの組織が、Teams 会議の機能を利用するためのものです。|
|SfBWithTeamsCollab<sup>2</sup>|Skype for Business|Skype for Business|あり|より緊密な管理制御を必要とする複雑な組織向けの、代替の開始地点。|
|SfBOnly|Skype for Business|Skype for Business|なし<sup>3</sup>|データ制御に関する厳密な要件が存在する組織向けの特殊なシナリオ。 Teams は、他のユーザーがスケジュールした会議に参加する場合にのみ使用します。|
||||||

</br>
</br>

**注:**

<sup>1</sup> 既存の (Teams または Skype for Business でスケジュールされた) 会議に参加できるかどうかは、モードによって制御されません。 既定では、ユーザーは常に招待されたすべての会議に参加できます。

<sup>2</sup> SfBWithTeamsCollab と SfBWithTeamsCollabAndMeetings は現在 PowerShell でのみ使用可能です。  完全なクライアント エクスペリエンスが提供された後は、これらのモードは管理ポータルで使用できるようになります。 

<sup>3</sup> Teams では現在、チームとチャンネル機能を無効にすることはできないため、今の段階では有効のままとなります。



## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: 移行と共存の管理

TeamsUpgradePolicy は、Mode と NotifySfbUsers の 2 つの主要プロパティを示しています。 
</br>
</br>

|パラメーター|型|使用できる値</br>(斜体が既定値)|説明|
|---|---|---|---|
|Mode|列挙|*アイランド*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|クライアントの実行モードを示します。|
|NotifySfbUsers|ブール|*false* または true|Skype for Business が間もなく Teams に置き換えられることをユーザーに知らせるバナーをクライアントに表示するかどうかを示します。 Mode=TeamsOnly の場合、これを true にすることはできません。|
|||||

Teams は TeamsUpgradePolicy のすべての関連するインスタンスを、組み込みの読み取り専用ポリシーを使用して提供します。 したがって、使用できるコマンドレットは Get と Grant のみとなります。 組み込みのインスタンスを次に示します。
</br>
</br>

|Identity|Mode|NotifySfbUsers|
|---|---|---|
|アイランド|アイランド|False|
|IslandsWithNotify|アイランド|True|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|True|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|
|UpgradeToTeams|TeamsOnly|False|
|Global</br>*既定値*|アイランド|False|
||||

これらのポリシー インスタンスは、個々のユーザーに付与することも、テナント全体に付与することもできます。 次に例を示します。
- ユーザー ($SipAddress) を Teams にアップグレードするには、"UpgradeToTeams" インスタンスを付与します。</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- テナント全体をアップグレードするには、grant コマンドから Identity パラメーターを省略します。</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>フェデレーションに関する考慮事項

Skype for Business を使用している他のユーザーへの Teams からのフェデレーションには、Teams ユーザーが Skype for Business のオンラインに所属している必要があります。 最終的には、オンプレミスの Skype for Business に所属している Teams ユーザーは、Teams のみのユーザーとフェデレーションを行うことができるようになります。

TeamsUpgradePolicy は、フェデレーションされた受信チャットと通話のルーティングを制御します。 フェデレーションされたルーティングの動作は、同じテナントの場合のシナリオと同じものです (*アイランド モードの場合を除く*)。  受信者がアイランド モードの場合の動作は、次のようになります。 
- Teams から開始されたチャットと通話は、受信者が*フェデレーションされたテナント*にいる場合、Skype for Business に届きます。
- Teams から開始されたチャットと通話は、受信者が*同じテナント*にいる場合、Teams に届きます。
- Skype for Business から開始されたチャットと通話は常に、Skype for Business に届きます。

詳細については、「[Skype for Business と共存する](https://docs.microsoft.com/ja-JP/MicrosoftTeams/coexistence-chat-calls-presence)」を参照してください。

## <a name="the-intended-client-user-experience-in-teams-when-using-sfb-modes"></a>Skype for Business モードを使用する場合に意図される、Teams でのクライアント ユーザー エクスペリエンス
ユーザーが Skype for Business モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) のいずれかの場合、すべての受信チャットと通話はユーザーの Skype for Business クライアントにルーティングされます。 エンド ユーザーが混乱することを回避し、適切なルーティングを実現するため、Teams クライアントの通話とチャット機能は、*ユーザーがいずれかの Skype for Business モードにある場合は無効になるように意図されています*。 同様に、Teams での会議のスケジュールも、*ユーザーが SfBOnly または SfBWithTeamsCollab モードの場合は明示的に無効になるように*、そしてユーザーが SfBWithTeamsCollabAndMeetings の場合に明示的に有効になるように意図されています。 

### <a name="automatic-conformance-of-teams-client-based-on-mode-planned"></a>モードに基づいた Teams クライアントの自動適合 (予定) 
チャットと通話機能を自動的に無効にする機能と、会議のスケジュールをモードに基づいて有効/無効にする機能が、TAP のお客様に対して展開され始めましたが、まだ幅広く利用いただける段階にはありません。 この新機能の詳細については、「[Teams のクライアント エクスペリエンスおよび共存モードへの準拠](https://docs.microsoft.com/ja-JP/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)」を参照してください。

### <a name="manual-configuration-of-workload-policy-settings-prior-to-automatic-conformance"></a>自動適合前の、手動によるワークロード ポリシー設定の構成
モードへの自動適合に関するこのソリューションが提供されるまでは、管理者は TeamsMessagingPolicy、TeamsCallingPolicy、TeamsMeetingPolicy の値を手動で構成することにより、TeamsUpgradePolicy モードの対象のクライアント エクスペリエンスを適用することができます。 さらに、PowerShell で `Grant-CsTeamsUpgradePolicy` を使用するときに、TeamsMessagingPolicy、TeamsCallingPolicy、TeamsMeetingPolicy 内の対応する設定の構成がコマンドレットによりチェックされ、これらの設定が指定のモードと互換性があるかどうかが確認されます。 いずれかが正しく構成されていない場合、grant 処理は続行されますが、正しく構成されていない設定を示す警告が表示されます。 管理者は引き続き示されたポリシーを更新して、Teams に互換性のあるエンド ユーザー エクスペリエンスを提供する必要があります。 管理者が警告の結果として何も対応しないことを決めた場合でも、TeamsMessagingPolicy、TeamsCallingPolicy、TeamsMeetingPolicy の値に応じて、ユーザーは Teams のチャット、通話、会議スケジュール機能を利用できますが、エンド ユーザー エクスペリエンスがわかりにくくなる可能性があります。

TeamsUpgadePolicy が付与されたときにチェックされるポリシー設定に関する詳細については、「[Teams のクライアント エクペリエンスおよび共存モードへの準拠](https://docs.microsoft.com/ja-JP/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)」を参照してください。


**注:** 上述のクライアント動作の自動適用が提供される前は、各 Skype for Business モードは基本的に同じように動作します。 SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings モードでの受信通話とチャットのルーティング方法はすべて同じです。 現時点での唯一の違いは、Teams と Skype for Business 用の Outlook アドインが有効であるかどうかです。 差別化されたクライアントのエクスペリエンスが提供されるまでは、Skype for Business モードの 1 つのみが管理ポータルで有効にされます。 ただし、すべてのモードは PowerShell で使用できます。


## <a name="teamsinteroppolicy-and-legacy-mode-has-been-retired"></a>TeamsInteropPolicy と Legacy モードの廃止 

TeamsInteropPolicy は TeamsUpgradePolicy に置き換えられました。 以前 TeamsInteropPolicy を優先していたすべてのコンポーネントが、代わりに TeamsUpgradePolicy を優先するように更新されました。  Microsoft は以前、TeamsInteropPolicy から TeamsUpgradePolicy への移行を促進するため、TeamsUpgradePolicy に "Legacy" モードを導入しました。 Legacy モードでは、TeamsUpgradePolicy を理解していたルーティング コンポーネントは TeamsInteropPolicy に戻されました。 ルーティングは現在 TeamsUpgradePolicy を完全にサポートしています。 現在、Legacy モードはサポートされなくなっており、Legacy モードを付与することもできません。


## <a name="detailed-mode-descriptions"></a>モードの詳細な説明
</br>
</br>

|Mode|説明 (予定されているクライアント エクスペリエンスを含む)|
|---|---|
|**アイランド**</br>(既定)|ユーザーは Skype for Business と Teams の両方を並べて実行します。 このユーザーは、</br><ul><li>Skype for Business または Teams クライアントのいずれかでチャットと VOIP 通話を開始できます。 オンプレミスの Skype for Business に所属しているユーザーは、受信者のモードに関わらず、Teams から他の Skype for Business ユーザーに対して連絡することはできません。<li>他のユーザーが Skype for Business で開始したチャットと VOIP 通話を、自分の Skype for Business クライアントで受信します。<li>他のユーザーが Teams で開始したチャットと VOIP 通話を、そのユーザーが*同じテナント*にいる場合、自分の Teams クライアントで受信します。<li>他のユーザーが Teams で開始したチャットと VOIP 通話を、そのユーザーが*フェデレーションされたテナント*にいる場合、自分の Skype for Business クライアントで受信します。 <li>次に示すような、PSTN 機能があります。<ul><li>ユーザーがオンプレミスの Skype for Business に所属している場合、PSTN 通話が開始され、Skype for Business で受信されます。<li>ユーザーがオンラインに所属している場合、ユーザーには電話システムがあり、その場合ユーザーは、<ul><li>ダイレクト ルーティング用に構成されていれば、Teams で PSTN 通話の開始と受信を行います。<li>MS 通話プランを利用しているか、Skype for Business クラウド コネクタ エディションまたは Skype for Business Server のオンプレミス展開 (ハイブリッド音声) 経由で PSTN ネットワークに接続している場合は、Skype for Business で PSTN 通話の開始と受信を行います。</ul></ul><li>Teams または Skype for Business で会議をスケジュールすることができます (また、既定では両方のプラグインが表示されます)。<li>Skype for Business または Teams のあらゆる会議に参加できます。会議はそれぞれのクライアントで開きます。</ul>|
|**SfBOnly**|ユーザーは Skype for Business のみを実行します。 このユーザーは、</br><ul><li>Skype for Business からのみチャットと通話を開始することができます。<li>オンプレミスの Skype for Business に所属している Teams ユーザーが開始したものでない限り、すべてのチャット/通話を開始元に関わらず自分の Skype for Business クライアントで受信します。*<li>Skype for Business の会議のみスケジュールできます。ただし、Skype for Business 会議と Teams 会議のいずれにも参加することができます。</br>\** オンプレミスのユーザーにアイランド モードを使用することは、他の SfBOnly モードのユーザーとの組み合わせにおいて、お勧めできません。 オンプレミスの Skype for Business に所属している Teams ユーザーが、SfBOnly ユーザーに対して通話またはチャットを開始した場合、SfBOnly ユーザーには届かず、届かなかったチャット/通話に関する電子メールが送られます。*|
|**SfBWithTeamsCollab**|ユーザーは Skype for Business と Teams の両方を並べて実行します。 このユーザーは、</br><ul><li>SfBOnly モードのユーザーと同じ機能があります。<li>Teams をグループでの共同作業 (チャネル) に関してのみ利用できます。チャット/通話/会議のスケジュールは利用できません。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|ユーザーは Skype for Business と Teams の両方を並べて実行します。 このユーザーは、<ul><li>SfBOnly モードのユーザーと同じチャットと通話機能があります。<li>Teams をグループでの共同作業 (チャネル (チャネル会話を含む)) に対してのみ利用できます。チャットと通話は利用できません。<li>Teams 会議のみスケジュールできます。ただし、Skype for Business 会議と Teams 会議のいずれにも参加することができます。</ul>|
|**TeamsOnly**</br>(Skype for Business Online に所属していることが必要)|ユーザーは Teams のみ実行します。 このユーザーは、<ul><li>すべてのチャットと通話を開始元に関わらず自分の Teams クライアントで受信します。<li>Teams からのみチャットと通話を開始することができます。<li>Teams でのみ会議をスケジュールできます。ただし、Skype for Business 会議と Teams 会議のいずれにも参加することができます。<li>Skype for Business IP 電話を使用し続けることができます。</ul> |
|||




## <a name="related-topics"></a>関連項目

[Skype for Business と共存する](https://docs.microsoft.com/ja-JP/MicrosoftTeams/coexistence-chat-calls-presence)

[Teams のクライアント エクスペリエンスおよび共存モードへの準拠](https://docs.microsoft.com/ja-JP/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)


