---
title: 移行と相互運用性-Skype for Business
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams への移行を管理するためのガイダンス
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf12dc366de030329b306fdd2f68291b5ff532d
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140276"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス

> [!Tip] 
> [共存および相互運用性の詳細については、こちらのセッション](https://aka.ms/teams-upgrade-coexistence-interop)をご覧ください。

Skype for Business を使用する組織が Teams を導入するとき、管理者は TeamsUpgradePolicy のプロパティである共存 "モード" の概念を使用して、組織のユーザー エクスペリエンスを管理することができます。 モードを使用すると、管理者は Skype for Business から Teams への切り替えを管理するときに、相互運用と移行を管理することができます。  ユーザーのモードによって、受信チャットと通話が届くクライアントと、新しい会議がスケジュールされるサービス (Teams または Skype for Business) が決定されます。 また、Teams クライアントで使用可能な機能も管理します。 


## <a name="fundamental-concepts"></a>基礎概念

1.  *相互運用性* : Lync/Skype for Business ユーザーと Teams ユーザーの間の 1 対 1 の通信。

2.  *フェデレーション*: さまざまなテナントのユーザー間の通信。

3.  すべての Teams ユーザーには、"自宅" の Skype for Business アカウントがあります。これは、オンラインまたはオンプレミスのいずれかになります。
    - 既に Skype for Business Online を使用しているユーザーは、既存のオンライン アカウントを使用します。
    - 既にオンプレミスの Skype for Business/Lync を使用しているユーザーは、既存のオンプレミス アカウントを使用します。
    - 既存の Skype for Business アカウントが検出できないユーザーの場合、Teams ユーザーが作成されたときに、Skype for Business Online アカウントが自動的にプロビジョニングされます。

4.  Skype for Business または Lync いずれかのオンプレミス展開が存在し、そのユーザーを Teams のユーザーとする必要がある場合は、Teams/Skype for Business Online によりオンプレミス環境が適切に検出されるよう、少なくとも Azure AD Connect が msRTCSIP-DeploymentLocator を AAD に同期していることを確認する必要があります。 さらに、どのユーザーを TeamsOnly モードに移行する (つまりユーザーをアップグレードする) 場合でも、*まず Skype for Business ハイブリッド モードを構成する必要があります*。 詳細については、[Skype for Business と Teams 向けの Azure AD Connect の構成](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)に関する記事を参照してください。

5.  Teams と Skype for Business ユーザー間の相互運用は、*Teams ユーザーが Skype for Business でオンラインに所属している場合のみ可能です*。 受信者となる Skype for Business ユーザーは、オンプレミス (Skype for Business ハイブリッドの構成が必要) またはオンラインに所属できます。 オンプレミスの Skype for Business に所属しているユーザーはアイランド モード (このドキュメントの後で定義されます) で Teams を使用できますが、Skype for Business を使用している他のユーザーとの相互運用またはフェデレーションのために Teams を使用することはできません。  

6.    アップグレードと相互運用の動作は、後で説明するユーザーの共存モードに基づいて決定されます。 モードは、TeamsUpgradePolicy によって管理されます。 

7.  ユーザーを TeamsOnly モードにアップグレードすることにより、発信元のクライアントとは無関係に、すべての受信チャットと通話がユーザーの Teams クライアントに常に届くようになります。 また、アップグレードされたユーザーは新しい会議を Teams でスケジュールするようになります。 TeamsOnly モードにするには、ユーザーが Skype for Business でオンラインに所属している必要があります。 これは、Teams ユーザーの確実な相互運用、フェデレーション、完全な管理のために必要です。 ユーザーを TeamsOnly にアップグレードするには、次の操作を実行します。
    - ユーザーが Skype for Business Online に所属している (または Skype アカウントを所有したことがない) 場合、PowerShell で "UpgradeToTeams" を使用して、Mode=TeamsOnly で TeamsUpgradePolicy をそのユーザーに付与します。または、Teams 管理センターを使用して TeamsOnly モードを選択します。
    - ユーザーがオンプレミスに所属している場合、オンプレミスの管理ツールから `Move-CsUser` を使用して、まずそのユーザーを Skype for Business Online に移動します。  Skype for Business Server 2019 または CU8 for Skype for Business Server 2015 をお持ちの場合、`Move-CsUser` で `-MoveToTeams` スイッチを指定して、オンラインへの移行の一環としてユーザーを直接 Teams に移動することができます。 このオプションは、ユーザーの会議も Teams に移行します。 `-MoveToTeams` が指定されていないか使用できない場合、`Move-CsUser` の完了後に PowerShell または Teams 管理センターを使用して、TeamsOnly モードをそのユーザーに割り当てます。 詳細については、「[ユーザーのオンプレミスとクラウド間の移動](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)」を参照してください。  会議の移行の詳細については、「[会議移行サービス (MMS) の使用](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。

8.    ユーザーが Microsoft 電話システムを Teams で使用するには、TeamsOnly モードである (つまり、Skype for Business Online に所属しており、Teams にアップグレードされている) 必要があります。また、Microsoft 電話システムの[ダイレクト ルーティング](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) (自分の SIP トランクと SBC で電話システムを使用するための機能) 向けに構成されているか、または Office 365 通話プランを利用している必要があります。 アイランド モードでは、Microsoft 電話システムのダイレクト ルーティングはサポートされません。    

9.  ユーザーが Skype for Business Online またはオンプレミスの Skype for Business に所属しているかどうかに関係なく、電話会議 (PSTN 経由のダイヤルインまたはダイヤルアウト) を使用して Teams の会議をスケジュールできます。 


## <a name="coexistence-modes"></a>共存モード

相互運用と移行は、TeamsUpgradePolicy を使用した "共存モード" に基づいて管理されます。 共存モードは、組織が Skype for Business から Teams に移行するときに、シンプルで予測可能な操作環境をエンド ユーザーに提供します。 Teams に移行する組織にとって、各ユーザーの最終的な目的地は TeamsOnly モードですが、すべてのユーザーに TeamsOnly (またはその他のモード) を同時に割り当てる必要はありません。 ユーザーが TeamsOnly モードになる前は、Skype for Business モード (SfBOnly、Sfbwithteams、SfBWithTeamsCollabAndMeetings) のいずれかを使用して、teams のみで、かつまだ存在しないユーザー間で一貫した通信を行うことができます。


技術的な観点から見ると、ユーザーのモードは、ユーザーエクスペリエンスのいくつかの側面を制御します。

- *受信ルーティング*: 受信チャットと通話が、どのクライアント (Teams または Skype for Business) に届くのか。 
- *プレゼンス公開*: 他のユーザーに表示されるユーザーのプレゼンスが、Teams または Skype for Business のいずれのアクティビティに基づいたものなのか。 
- *会議のスケジュール*: 新しい会議のスケジュール、そして適切なアドインが Outlook に存在することを確認するのに使用されるサービスはどれなのか。 TeamsUpgradePolicy は会議への参加については制御しないことに注意してください。 ユーザーは常に、Skype for Business または Teams のいずれの会議であっても、*参加*することができます。
- *クライアント エクスペリエンス*: Teams または Skype for Business で利用可能な機能はどれなのか。 ユーザーは通話やチャットを、Teams または Skype for Business のいずれで開始できるのか、または両方で開始できるのか。 チームとチャンネルのエクスペリエンスは使用可能なのか。  

モードに基づくルーティングとプレゼンスの動作の詳細については、「[Skype for Business との共存](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence)」を参照してください。

一方で、エクスペリエンスの観点からは、モードは次のエクスぺリエンスを定義するものであると、よりシンプルに説明することができます。
- *チャットと通話*: ユーザーが使用するクライアントはどれなのか。
- *会議のスケジュール*: ユーザーは新しい会議を Teams と Skype for Business のいずれの会議としてスケジュールするのか。
- *Teams クライアントでの共同作業機能の使用可能性*。 ユーザーがまだ Skype for Business を所有している場合、チームとチャンネル、およびファイル機能を使用できるかどうか。

モードの一覧を次に示します。
</br>
</br>

|モード|通話とチャット|会議のスケジュール<sup>1</sup>|チームとチャンネル|使用例|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Skype for Business Online に所属していることが必要*|Teams|Teams|あり|アップグレード過程の最終的な状態。 新しいテナントの既定値でもあります。|
|アイランド|いずれか|いずれか|あり|既定の構成。 1 人のユーザーが両方のクライアントを並べて比較することができます。 チャットと通話はいずれかのクライアントに届くので、ユーザーは両方のクライアントを常に起動しておく必要があります。 Skype for Business エクスペリエンスが複雑化または低下することを回避するため、外部 (フェデレーション) コミュニケーション、PSTN 音声サービスと音声アプリケーション、Office の統合、その他のいくつかの統合は引き続き Skype for Business で処理されます。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|あり|"会議優先"。 主に、通話のクラウドへの移行準備ができていないオンプレミスの組織が、Teams 会議の機能を利用するためのものです。|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|はい|より緊密な管理制御を必要とする複雑な組織向けの、代替の開始地点。|
|SfBOnly|Skype for Business|Skype for Business|いいえ<sup>3</sup>|データ制御に関する厳密な要件が存在する組織向けの特殊なシナリオ。 Teams は、他のユーザーがスケジュールした会議に参加する場合にのみ使用します。|
||||||

</br>
</br>

**注:**

<sup>1</sup> 既存の (Teams または Skype for Business でスケジュールされた) 会議に参加できるかどうかは、モードによって制御されません。 既定では、ユーザーは常に招待されたすべての会議に参加できます。

<sup>2</sup> 既定では、個々のユーザーに TeamsOnly または SfbWithTeamsCollabAndMeetings を割り当てる場合、そのユーザーが将来予定している既存の Skype for Business 会議は Teams 会議に変換されます。 必要に応じて、TeamsUpgradePolicy を付与する際に `-MigrateMeetingsToTeams $false` を指定するか、Teams 管理ポータルのチェックボックスをオフにして、これらの会議を Skype for Business 会議として残すことができます。   テナント全体で TeamsUpgradePolicy を付与する場合、Skype for Business から Teams に会議を変換することはできません。 

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

Skype for Business を使用している他のユーザーへの Teams からのフェデレーションには、Teams ユーザーが Skype for Business のオンラインに所属している必要があります。

TeamsUpgradePolicy は、フェデレーションされた受信チャットと通話のルーティングを制御します。 フェデレーションされたルーティングの動作は、同じテナントの場合のシナリオと同じものです (*アイランド モードの場合を除く*)。  受信者がアイランド モードの場合の動作は、次のようになります。 
- Teams から開始されたチャットと通話は、受信者が*フェデレーションされたテナント*にいる場合、Skype for Business に届きます。
- Teams から開始されたチャットと通話は、受信者が*同じテナント*にいる場合、Teams に届きます。
- Skype for Business から開始されたチャットと通話は常に、Skype for Business に届きます。

詳細については、「[Skype for Business と共存する](https://docs.microsoft.com/MicrosoftTeams/coexistence-chat-calls-presence)」を参照してください。

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>Skype for Business モードを使用する場合の Teams クライアント ユーザー エクスペリエンス
ユーザーが Skype for Business モード (SfBOnly、SfbwithteamsSfBWithTeamsCollabAndMeetings) を使用している場合、着信するすべてのチャットと通話はユーザーの Skype for Business クライアントにルーティングされます。 ユーザーがいずれかの Skype for Business モードに設定されている場合、エンド ユーザーを混乱させない適切なルーティングを確保するために、Teams クライアントの通話とチャット機能は自動的に無効化されます。 同様に、Teams での会議のスケジュールも、ユーザーが SfBOnly モードまたは SfBWithTeamsCollab モードの場合は自動的に無効化され、ユーザーが SfBWithTeamsCollabAndMeetings モードの場合には自動的に有効化されます。 詳細については、「[Teams のクライアント エクスペリエンスおよび共存モードへの準拠](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)」を参照してください。

> [!Note] 
> - Teams と Channels の自動適用を行う前に、SfbOnly と SfBWithTeamsCollab モードは同じように動作します。


## <a name="detailed-mode-descriptions"></a>モードの詳細な説明
</br>
</br>

|モード|説明|
|---|---|
|**アイランド**</br>(既定)|ユーザーは Skype for Business と Teams の両方を並べて実行します。 このユーザーは、</br><ul><li>Skype for Business または Teams クライアントのいずれかでチャットと VoIP 通話を開始できます。 オンプレミスの Skype for Business に所属しているユーザーは、受信者のモードに関わらず、Teams から他の Skype for Business ユーザーに対して連絡することはできません。<li>他のユーザーが Skype for Business で開始したチャットと VoIP 通話を、自分の Skype for Business クライアントで受信します。<li>他のユーザーが Teams で開始したチャットと VoIP 通話を、そのユーザーが*同じテナント*にいる場合、自分の Teams クライアントで受信します。<li>他のユーザーが Teams で開始したチャットと VoIP 通話を、そのユーザーが*フェデレーションされたテナント*にいる場合、自分の Skype for Business クライアントで受信します。 <li>次に示すような、PSTN 機能があります。<ul><li>ユーザーがオンプレミスの Skype for Business に所属していてエンタープライズ VoIP を持っている場合、常に PSTN 通話が開始され、Skype for Business で受信されます。<li>ユーザーがオンプレミスの Skype for Business Online に所属していて Microsoft 電話システムを使用している場合、ユーザーは常に Skype for Business の PSTN 通話を開始および受信します。<ul><li>これは、Microsoft 通話プランを利用しているか、Skype for Business クラウド コネクタ エディションまたは Skype for Business Server のオンプレミス展開 (ハイブリッド音声) 経由で PSTN ネットワークに接続しているかに関係なく発生します。<li>**注: アイランド モードでは、Microsoft Teams 電話システムのダイレクト ルーティングはサポートされません。**</ul></ul><li>Skype for Business で Microsoft 通話キューと自動応答通話を受信します。<ul><li>通話キューおよび自動応答に割り当てられた電話番号は、アイランドモードの Microsoft Teams の電話システムによるダイレクト ルーティングでは**ありません**。</ul></ul><li>Teams または Skype for Business で会議をスケジュールすることができます (また、既定では両方のプラグインが表示されます)。<li>Skype for Business または Teams のあらゆる会議に参加できます。会議はそれぞれのクライアントで開きます。</ul>|
|**SfBOnly**|ユーザーは Skype for Business のみを実行します。 このユーザーは、</br><ul><li>Skype for Business からのみチャットと通話を開始することができます。<li>オンプレミスの Skype for Business に所属している Teams ユーザーが開始したものでない限り、すべてのチャット/通話を開始元に関わらず自分の Skype for Business クライアントで受信します。*<li>Skype for Business の会議のみスケジュールできます。ただし、Skype for Business 会議と Teams 会議のいずれにも参加することができます。</br>\** オンプレミスのユーザーにアイランド モードを使用することは、他の SfBOnly モードのユーザーとの組み合わせにおいて、お勧めできません。 オンプレミスの Skype for Business に所属している Teams ユーザーが、SfBOnly ユーザーに対して通話またはチャットを開始した場合、SfBOnly ユーザーには届かず、届かなかったチャット/通話に関する電子メールが送られます。*|
|**SfBWithTeamsCollab**|ユーザーは Skype for Business と Teams の両方を並べて実行します。 このユーザーは、</br><ul><li>SfBOnly モードのユーザーと同じ機能があります。<li>Teams をグループでの共同作業 (チャネル) に関してのみ利用できます。チャット/通話/会議のスケジュールは利用できません。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|ユーザーは Skype for Business と Teams の両方を並べて実行します。 このユーザーは、<ul><li>SfBOnly モードのユーザーと同じチャットと通話機能があります。<li>Teams をグループでの共同作業 (チャネル (チャネル会話を含む)) に対してのみ利用できます。チャットと通話は利用できません。<li>Teams 会議のみスケジュールできます。ただし、Skype for Business 会議と Teams 会議のいずれにも参加することができます。</ul>|
|**TeamsOnly**</br>(Skype for Business Online に所属していることが必要)|ユーザーは Teams のみ実行します。 このユーザーは、<ul><li>すべてのチャットと通話を開始元に関わらず自分の Teams クライアントで受信します。<li>Teams からのみチャットと通話を開始することができます。<li>Teams でのみ会議をスケジュールできます。ただし、Skype for Business 会議と Teams 会議のいずれにも参加することができます。<li>Skype for Business IP 電話を使用し続けることができます。<br><br>*チームの導入が飽和状態になるまでは、Teams を使用して他のユーザーと別のユーザーと組み合わせて使用することはお勧めできません。つまり、すべての孤島モードのユーザーは、チームと Skype for Business クライアントの両方を積極的に使用および監視します。チームのユーザーのみが発信またはチャットを開始した場合は、その呼び出しまたはチャットが諸島ユーザーのチームクライアントに表示されます。島々ユーザーが Teams を使用しないか監視している場合、そのユーザーはオフラインとして表示され、チームのユーザーのみがアクセスできなくなります。*</ul> |
|||




## <a name="related-topics"></a>関連項目

[Skype for Business と共存する](https://docs.microsoft.com/microsoftteams/coexistence-chat-calls-presence)

[Teams のクライアント エクスペリエンスおよび共存モードへの準拠](https://docs.microsoft.com/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Meeting Migration Service (MMS) の使用](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
