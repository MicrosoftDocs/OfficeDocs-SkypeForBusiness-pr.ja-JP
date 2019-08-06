---
title: Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: e6656cab6918cfa0b04da28f0197137a300bbf79
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207194"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス

> [!Tip] 
> [共存および相互運用性の詳細については、こちらのセッション](https://aka.ms/teams-upgrade-coexistence-interop)をご覧ください。

Skype for Business を使用する組織が Teams を導入するとき、管理者は TeamsUpgradePolicy のプロパティである共存 "モード" の概念を使用して、組織のユーザー エクスペリエンスを管理することができます。 モードを使用すると、管理者は Skype for Business から Teams への切り替えを管理するときに、相互運用と移行を管理することができます。  ユーザのモードによって、どのクライアントがどのような通話を受け、どのサービス (Teams または Skype for Business) の新しい会議がスケジュールされるかが決まります。 また、Teams クライアントで使用できる機能も管理します。 


## <a name="fundamental-concepts"></a>基礎概念

1.  *相互運用性* : Lync/Skype for Business ユーザーと Teams ユーザーの間の 1 対 1 の通信。

2.  *フェデレーション*: さまざまなテナントのユーザー間の通信。

3.  Teams ユーザーはすべて、オンラインまたはオンプレミスのいずれかに "所属" する、基本の Skype for Business アカウントを所有しています。
    - 既に Skype for Business Online を使用しているユーザーは、既存のオンライン アカウントを使用します。
    - 既にオンプレミスの Skype for Business/Lync を使用しているユーザーは、既存のオンプレミス アカウントを使用します。
    - 既存の Skype for Business アカウントが検出できないユーザーの場合、Teams ユーザーが作成されたときに、Skype for Business Online アカウントが自動的にプロビジョニングされます。

4.  Skype for Business または Lync いずれかのオンプレミス展開が存在し、そのユーザーを Teams のユーザーとする必要がある場合は、Teams/Skype for Business Online によりオンプレミス環境が適切に検出されるよう、少なくとも Azure AD Connect が msRTCSIP-DeploymentLocator を AAD に同期していることを確認する必要があります。 さらに、どのユーザーを TeamsOnly モードに移行する (つまりユーザーをアップグレードする) 場合でも、*まず Skype for Business ハイブリッド モードを構成する必要があります*。 詳細については、[Skype for Business と Teams 向けの Azure AD Connect の構成](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect)に関する記事を参照してください。

5.  Teams と Skype for Business ユーザー間の相互運用は、*Teams ユーザーが Skype for Business でオンラインに所属している場合のみ可能です*。 受信者となる Skype for Business ユーザーは、オンプレミス (Skype for Business ハイブリッドの構成が必要) またはオンラインに所属できます。 オンプレミスの Skype for Business に所属しているユーザーはアイランド モード (このドキュメントの後で定義されます) で Teams を使用できますが、Skype for Business を使用している他のユーザーとの相互運用またはフェデレーションのために Teams を使用することはできません。  

6.  アップグレードと相互運用の動作は、後で説明するユーザーの共存モードに基づいて決定されます。 モードは、TeamsUpgradePolicy によって管理されます。 

7.  ユーザーを TeamsOnly モードにアップグレードすると、送信元のクライアントの種類に関係なく、すべての着信チャットと通話が常にユーザーのチームクライアントに表示されます。 また、アップグレードされたユーザーは新しい会議を Teams でスケジュールするようになります。 TeamsOnly モードにするには、ユーザーが Skype for Business でオンラインに所属している必要があります。 これは、Teams ユーザーの確実な相互運用、フェデレーション、完全な管理のために必要です。ユーザーを TeamsOnly にアップグレードするには、次の操作を実行します。
    - ユーザーが Skype for Business Online に所属している (または Skype アカウントを所有したことがない) 場合、PowerShell で "UpgradeToTeams" を使用して、Mode=TeamsOnly で TeamsUpgradePolicy をそのユーザーに付与します。または、Teams 管理センターを使用して TeamsOnly モードを選択します。
    - ユーザーがオンプレミスに所属している場合、オンプレミスの管理ツールから `Move-CsUser` を使用して、まずそのユーザーを Skype for Business Online に移動します。  Skype for Business Server 2019 または CU8 for Skype for Business Server 2015 をお持ちの場合、`Move-CsUser` で `-MoveToTeams` スイッチを指定して、オンラインへの移行の一環としてユーザーを直接 Teams に移動することができます。 このオプションでは、ユーザーの会議も Teams に移行されます。 `-MoveToTeams` が指定されていないか使用できない場合、`Move-CsUser` の完了後に PowerShell または Teams 管理センターを使用して、TeamsOnly モードをそのユーザーに割り当てます。 詳細については、「[ユーザーのオンプレミスとクラウド間の移動](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)」を参照してください。  会議の移行の詳細については、「[会議移行サービス (MMS) の使用](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。

8.  Microsoft 電話システムを Teams と共に使用するには、ユーザーが TeamsOnly モード (Skype for Business Online に所属し、チームにアップグレードされます) を使用している必要があります。また、Microsoft Phone システムの[ダイレクトルーティング](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277)用に構成する必要があります (これにより、電話システムを使うことができます。自分の SIP trunks と SBC) か、Office 365 通話プランを利用できます。 島々モードでは、Microsoft Phone システムのダイレクトルーティングはサポートされません。    

9.  電話会議 (PSTN 経由のダイヤルインまたはダイヤルアウト) でのチーム会議のスケジュールは、ユーザーが Skype for Business Online と Skype for Business のオンプレミスのどちらを使用しているかに関係なく利用できます。 


## <a name="coexistence-modes"></a>共存モード

相互運用と移行は、TeamsUpgradePolicy を使用する "共存モード" に基づいて管理されます。 共存モードは、組織が Skype for Business から Teams に移行するときに、シンプルで予測可能な操作環境をエンド ユーザーに提供します。 Teams に移行する組織にとって、各ユーザーの最終的な目的地は TeamsOnly モードですが、すべてのユーザーに TeamsOnly (またはその他のモード) を同時に割り当てる必要はありません。 ユーザーが TeamsOnly モードに到達する前に、組織は Skype for Business の任意のモード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) を使用して、TeamsOnly であるユーザーとまだ TeamsOnly ではないユーザー間の予測可能な通信を確保することができます。


技術的な観点からは、ユーザーのモードによってユーザーの操作環境のいくつかの側面が制御されます。

- *受信ルーティング*: 受信チャットと通話が、どのクライアント (Teams または Skype for Business) に届くのか。 
- *プレゼンス公開*: 他のユーザーに表示されるユーザーのプレゼンスが、Teams または Skype for Business のいずれのアクティビティに基づいたものなのか。 
- *会議のスケジュール*: 新しい会議のスケジュールを設定し、Outlook に適切なアドインが存在するかどうかを確認するために使用されるサービスはどれですか。 TeamsUpgradePolicy は会議への参加については制御しないことに注意してください。 ユーザーは常に、Skype for Business または Teams のいずれの会議であっても、*参加*することができます。
- *クライアント エクスペリエンス*: Teams または Skype for Business で利用可能な機能はどれなのか。 ユーザーは通話やチャットを、Teams または Skype for Business のいずれで開始できるのか、または両方で開始できるのか。 チームとチャンネルのエクスペリエンスは使用可能なのか。  

モードに基づくルーティングとプレゼンスの動作の詳細については、「[Skype for Business との共存](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence)」を参照してください。

一方で、エクスペリエンスの観点からは、モードは次のエクスぺリエンスを定義するものであると、よりシンプルに説明することができます。
- *チャットと通話*: ユーザーが使用するクライアントはどれなのか。
- *会議のスケジュール*: ユーザーは新しい会議を Teams と Skype for Business のいずれの会議としてスケジュールするのか。
- *Teams クライアントでの共同作業機能の使用可能性*。 ユーザーがまだ Skype for Business を所有している場合、チームとチャンネル、およびファイル機能を使用できるかどうか。

モードの一覧を次に示します。
</br>
</br>

|モード|通話とチャット|会議のスケジュール<sup>1</sup>|チームとチャンネル|使用例|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Skype for Business Online に所属していることが必要*|Teams|Teams|はい|アップグレード過程の最終的な状態。 シートが 500 未満の新しいテナントの既定値でもあります。|
|アイランド|いずれか|いずれか|はい|既定の構成。 1人のユーザーが両方のクライアントを並べて評価することを許可します。 チャットと通話はいずれかのクライアントに届くので、ユーザーは両方のクライアントを常に起動しておく必要があります。 混乱または regressed の Skype for Business エクスペリエンスを回避するため、外部 (フェデレーション) 通信、PSTN 音声サービスと音声アプリケーション、Office の統合、その他のいくつかの統合は、引き続き Skype for Business で処理されます。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|あり|"会議優先"。 主に、オンプレミスの組織向けに、クラウドへの通話を移行する準備がまだできていない場合は、Teams の会議機能を活用できます。|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|あり|厳しく管理の制御が必要な複雑な組織のための代替の開始点です。|
|SfBOnly|Skype for Business|Skype for Business|なし<sup>3</sup>|データコントロールに関する厳格な要件を持つ組織向けの特殊なシナリオ。 Teams は、他のユーザーがスケジュールした会議に参加する場合にのみ使用します。|
||||||

</br>
</br>

**注:**

<sup>1</sup> 既存の (Teams または Skype for Business でスケジュールされた) 会議に参加できるかどうかは、モードによって制御されません。 既定では、ユーザーは常に招待されたすべての会議に参加できます。

<sup>2</sup>既定では、Teams sonly または SfbWithTeamsCollabAndMeetings を個々のユーザーに割り当てると、そのユーザーによって予定されている既存の Skype for business 会議が Teams 会議に変換されます。 必要に応じて、これらの会議を Skype for Business 会議のままに`-MigrateMeetingsToTeams $false`しておくには、TeamsUpgradePolicy を付与するか、Teams 管理ポータルのチェックボックスをオフにします。   Skype for Business から Teams への会議の変換機能は、テナント全体で TeamsUpgradePolicy を付与する場合は使用できません。 

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

詳細については、「[Skype for Business と共存する](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence)」を参照してください。

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>SfB モードを使用している場合の Teams クライアントのユーザーエクスペリエンス
ユーザーが Skype for Business モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) のいずれかの場合、すべての受信チャットと通話はユーザーの Skype for Business クライアントにルーティングされます。 ユーザーが Skype for Business モードのいずれかになっている場合、エンドユーザーの混乱を回避して、適切なルーティング、チームクライアントでの通話とチャットの機能が自動的に無効になるようにします。 同様に、Teams での会議のスケジュール設定は、ユーザーが sfbonly は Sfbwithteamsの [共同作業] モードになっている場合は自動的に無効になり、ユーザーが SfBWithTeamsCollabAndMeetings モードになったときに自動的に有効になります。 詳細については、「[チームクライアントエクスペリエンスと共存モードの準拠](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)」を参照してください。

> [!Note] 
> - チームとチャネルの自動実施が行われる前に、SfbOnly と Sfbwithteams の各モードは同じように動作します。


## <a name="detailed-mode-descriptions"></a>モードの詳細な説明
</br>
</br>

|Mode|解説|
|---|---|
|**アイランド**</br>(既定)|ユーザーは Skype for Business と Teams の両方を並べて実行します。 このユーザーは、</br><ul><li>Skype for Business または Teams クライアントで、チャットや VoIP 通話を開始できます。 オンプレミスの Skype for Business に所属しているユーザーは、受信者のモードに関わらず、Teams から他の Skype for Business ユーザーに対して連絡することはできません。<li>Skype for business クライアントの別のユーザーが、Skype for Business で開始された VoIP 通話 & チャットを受信します。<li>チームクライアント内の別のユーザーが*同じテナント*にいる場合に、チームで開始された & VoIP 通話を受信します。<li>フェデレーションされた*テナント*にいる場合は、Skype for business クライアントの別のユーザーが開始したチャット & VoIP 通話を受信します。 <li>次に示すような、PSTN 機能があります。<ul><li>ユーザーが Skype for Business をオンプレミスで使用しており、エンタープライズ Voip を利用している場合、PSTN 通話は常に Skype for Business で開始および受信されます。<li>ユーザーが Skype for Business Online をホームとしていて、Microsoft 電話システムを使用している場合、ユーザーは常に Skype for Business で PSTN 通話を開始および受信します。<ul><li>この問題が発生するのは、ユーザーが Microsoft の通話プランを使用しているかどうか、または Skype for business Cloud Connector Edition か、または Skype for Business Server (ハイブリッドボイス) のオンプレミス展開を介して PSTN ネットワークに接続しているかどうかに関係なく発生します。<li>**注: Microsoft Teams 電話システムのダイレクトルーティングは、島々モードではサポートされていません。**</ul></ul><li>Skype for Business で Microsoft 通話キューと自動応答の通話を受信します。<li>Teams または Skype for Business で会議をスケジュールすることができます (また、既定では両方のプラグインが表示されます)。<li>Skype for Business または Teams のあらゆる会議に参加できます。会議はそれぞれのクライアントで開きます。</ul>|
|**SfBOnly**|ユーザーは Skype for Business のみを実行します。 このユーザーは、</br><ul><li>Skype for Business からのみチャットと通話を開始することができます。<li>オンプレミスの Skype for Business に所属している Teams ユーザーが開始したものでない限り、すべてのチャット/通話を開始元に関わらず自分の Skype for Business クライアントで受信します。*<li>Skype for Business の会議のみスケジュールできます。ただし、Skype for Business 会議と Teams 会議のいずれにも参加することができます。</br>\** オンプレミスのユーザーにアイランド モードを使用することは、他の SfBOnly モードのユーザーとの組み合わせにおいて、お勧めできません。 オンプレミスの Skype for Business に所属している Teams ユーザーが、SfBOnly ユーザーに対して通話またはチャットを開始した場合、SfBOnly ユーザーには届かず、届かなかったチャット/通話に関する電子メールが送られます。*|
|**SfBWithTeamsCollab**|ユーザーは Skype for Business と Teams の両方を並べて実行します。 このユーザーは、</br><ul><li>SfBOnly モードのユーザーと同じ機能があります。<li>Teams をグループでの共同作業 (チャネル) に関してのみ利用できます。チャット/通話/会議のスケジュールは利用できません。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|ユーザーは Skype for Business と Teams の両方を並べて実行します。 このユーザーは、<ul><li>SfBOnly モードのユーザーと同じチャットと通話機能があります。<li>Teams をグループでの共同作業 (チャネル (チャネル会話を含む)) に対してのみ利用できます。チャットと通話は利用できません。<li>Teams 会議のみスケジュールできます。ただし、Skype for Business 会議と Teams 会議のいずれにも参加することができます。</ul>|
|**TeamsOnly**</br>(Skype for Business Online に所属していることが必要)|ユーザーは Teams のみ実行します。 このユーザーは、<ul><li>すべてのチャットと通話を開始元に関わらず自分の Teams クライアントで受信します。<li>Teams からのみチャットと通話を開始することができます。<li>Teams でのみ会議をスケジュールできます。ただし、Skype for Business 会議と Teams 会議のいずれにも参加することができます。<li>Skype for Business IP 電話を使用し続けることができます。<br><br>*チームの導入が飽和状態になるまでは、Teams を使用して他のユーザーと別のユーザーと組み合わせて使用することはお勧めできません。つまり、すべての孤島モードのユーザーは、チームと Skype for Business クライアントの両方を積極的に使用および監視します。チームのユーザーのみが発信またはチャットを開始した場合は、その呼び出しまたはチャットが諸島ユーザーのチームクライアントに表示されます。島々ユーザーが Teams を使用しないか監視している場合、そのユーザーはオフラインとして表示され、チームのユーザーのみがアクセスできなくなります。*</ul> |
|||




## <a name="related-topics"></a>関連項目

[Skype for Business と共存する](https://docs.microsoft.com/en-us/microsoftteams/coexistence-chat-calls-presence)

[Teams のクライアント エクスペリエンスおよび共存モードへの準拠](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[会議移行サービス (MMS) を使用する](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
