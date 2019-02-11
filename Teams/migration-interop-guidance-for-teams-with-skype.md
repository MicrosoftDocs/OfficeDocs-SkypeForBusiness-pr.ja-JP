---
title: Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: チームにビジネス用の Skype からの移行を管理するためのガイダンス
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e924311188e077e10e844b55e4a429ab5344dca
ms.sourcegitcommit: 3070dd7c091e6c97c6d746c6bfb866625184ba87
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "29786430"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス

> [!Tip] 
> [共存と相互運用性](https://aka.ms/teams-upgrade-coexistence-interop)について学習するのには次のセッションを見る

チームを採用するビジネス用の Skype で組織が開始されると、管理者が、共存の TeamsUpgradePolicy プロパティである「モード」の概念を使用して、組織内のユーザー エクスペリエンスを管理できます。 モードを使用すると、管理者は管理相互運用と移行チームにビジネス用の Skype からの移行を管理します。  ユーザーのモードでは、どのクライアントで受信したチャットと呼び出し土地にどのようなサービス (チームやビジネス用の Skype) の新しい会議をスケジュールします。 を決定します。 今後、モードがチームでどのような機能が表示されますクライアントの動作を定義するのにはも使用されます。 


## <a name="fundamental-concepts"></a>基本的な概念

1.  *相互運用機能*: ビジネス ・ ユーザーの Lync と Skype とチームのユーザーの間で 1 対 1 の通信です。

2.  *フェデレーション*: ユーザーが別のテナントの間の通信します。

3.  すべてのビジネス アカウントを「ホーム」いずれかのオンラインのユーザーが、基になる Skype をあるチームまたは設置。
    - 既に Skype を使用してオンライン ビジネスのユーザーは、既存のオンライン アカウントを使用します。
    - 既に Skype を使用する設置型のビジネスと Lync ユーザーは、既存のオンプレミス アカウントを使用します。
    - ユーザーが対象となる、既存の Skype のビジネス アカウントを検出できませんが、Skype のオンライン ビジネスのアカウント チームのユーザーが作成されるときに自動的に準備があります。 Skype ビジネス ライセンスが必要ではありません。

4.  ビジネスまたは Lync では、いずれかの Skype の設置型展開があるし、それらのユーザーのチームのユーザーに、最低限、必ず Azure AD 接続が msRTCSIP-DeploymentLocator を同期しているビジネスのチームと Skype は、そのために AAD、属性オンライン、オンプレミス環境を正しく検出します。 さらに、チーム専用のモードを任意のユーザーを移動する (つまり、アップグレード、ユーザー)、*ビジネスのハイブリッド モードの Skype を最初に構成する必要があります*。 詳細については、 [Skype のビジネスとチームの構成の Azure AD の接続](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect)を参照してください。

5.  ビジネス ユーザーのチームと Skype との間の相互運用機能は、使用可能な*ビジネス用の Skype でチームのユーザーは、オンライン ホーム サーバーの場合*だけです。 Skype ビジネス ユーザーが所属することができますか、オンプレミス (とビジネスのハイブリッドの Skype を設定する必要があります) の受信者またはオンラインです。 設置型のビジネスが Skype に置かれているユーザーは、(このドキュメントの後半で定義)、島のモードでチームを使用することができますが、チームを使用して、相互運用機能またはビジネスの Skype を使用して他のユーザーとフェデレーションを行うことはできません。  

6.  アップグレードと相互運用機能の動作は、TeamsUpgradePolicy で管理されているユーザーの共存モードに基づいて決定されます。 TeamsInteropPolicy は、受取済および許可モードではありません = レガシーは許可されていません。 

7.  TeamsOnly モードにユーザーをアップグレードする、すべての着信のチャットや通話は常にどのようなクライアントに関係なく、ユーザーのチームのクライアントに着陸できるようにから orignated を保証します。 これらのユーザー、チーム内のすべての新しい会議をスケジュールしてもします。 TeamsOnly モードにするには、ユーザーする必要がありますが所属するオンライン ビジネスの Skype にします。 これは、相互運用性、フェデレーション、およびチームのユーザーの完全な管理を確実に必要です。ユーザーを TeamsOnly にアップグレードするには。
    - ユーザーのオンライン ホーム ビジネスのための Skype の場合 (または任意の Skype アカウントがなかった)、モードで TeamsUpgradePolicy を与えた = PowerShell を使用して"UpgradeToTeams"のインスタンスを使用して TeamsOnly または TeamsOnly モードを選択するチームの管理センターを使用します。
    - 使用して、ユーザーがホームの設置型の場合は、 `Move-CsUser` 、設置から管理用ツールの最初の移動に Skype ユーザーは、オンライン ビジネスです。  かどうかがある Skype ビジネス サーバー 2019 または CU8 の Skype のビジネス サーバー 2015 の指定すること、`-MoveToTeams`でスイッチを`Move-CsUser`、移動の一部としてチームに直接ユーザーを移動するのにはオンラインです。 (ただし、ここでは、会議の移行のみタップ向け機能) このオプションはチームにもユーザーの会議を移行します。 場合`-MoveToTeams`は利用できない、または指定された後、`Move-CsUser`が完了したら、PowerShell またはチームの管理センターを使用してそのユーザーに TeamsOnly モードを割り当てます。  
     詳細は、[オンプレミスとクラウドの間でユーザーの移動](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)を参照してください。  会議の移行の詳細については、「[会議の移行サービス (MMS)](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。

8.  チームとチームの電話システムの機能を使用するユーザーは TeamsOnly モード (すなわち、Skype でオンライン ビジネスのホームをアップグレードしてチーム) である必要があり、マイクロソフトの電話システムに[直接ルーティングの場合](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277)(これは電話システムを使用できるように構成する必要がありますか独自の SIP トランクおよび SBC を使用して) を持つことも、Office 365 を呼び出すことを計画します。   

9.  オーディオ会議でチームのミーティングのスケジュール (ダイヤルインまたはダイヤルアウトを PSTN 経由で) は、オンライン ビジネスの Skype をホームとしているユーザーにのみ現在利用可能です。 オンプレミス Skype のビジネス アカウントでチームのユーザーのサポートは、タップでは。


## <a name="coexistence-modes"></a>共存モード

相互運用と移行は、TeamsUpgradePolicy を使用して「共存モード」に基づいて管理されます。 ユーザーのモードを決定します。

- *着信ルーティング*: クライアント (チームやビジネス用の Skype) は、どの着信チャットで着陸を呼び出しますか? 
- *会議のスケジュール設定*: 新しい会議をスケジュールしたり、適切なアドインが存在する Outlook でどのサービスを使用します。 TeamsUpgradePolicy では、会議の参加は制御されませんに注意してください。 ユーザーが常に*結合*すべての会議では、ビジネス会議やチーム会議、Skype であるかどうか。
- *クライアントで発生する*: どのような機能は、ビジネス クライアントのチームや Skype で利用できるでしょうか。 これは TeamsOnly モードを実装します。 他のモードのサポートは、今後の予定です。 

モードは次のとおりです。 SfBWithTeamsCollab と SfBWithTeamsCollabAndMeetings は、重複機能を持つが、両方のクライアントの混在の使用をことができません。 アイランド モードでは、機能が重複しているのですが、両方のクライアントの使用の状況を許可します。 たとえば、アイランド モードでは、ユーザーはビジネスやチームのいずれかの Skype でチャットを開始する可能性がありますが、SfBWithTeamsCollab で、できるだけチャット ビジネス用の Skype で (ただし、それらのチームのチャネルの会話に参加できます)。 あるデバイス モードのクライアントの expeirence がまだ完全に機能していないに注意してください。  
</br>
</br>

|モード|ルーティング動作|会議のスケジュール|クライアント エクスペリエンス|
|---|---|---|---|
|アイランド|VOIP の着信呼び出し、受信者の連合と島のモードで以外と発信者、同じクライアントでの着陸のチャット デバイス。<sup>1</sup>で着陸する場合に|両方|エンド ・ ユーザーは、呼び出しと、クライアントでは、チャットを開始できるし、クライアントの会議をスケジュールすることができます。|
|SfBOnly|着信呼び出しとのチャットは、Skype のビジネスにルーティングされます。|Skype for Business のみ|エンド ・ ユーザーでは、呼び出しとのみ、ビジネスの Skype のチャットを開始でき、のみ Skype のビジネス ・ ミーティングのスケジュールを設定することができます。 (適用されていません)|
|SfBWithTeamsCollab<sup>2</sup>|着信呼び出しとのチャットは、Skype のビジネスにルーティングされます。|Skype for Business のみ|エンド ・ ユーザーでは、呼び出しとのみ、ビジネスの Skype のチャットを開始でき、のみ Skype のビジネス ・ ミーティングのスケジュールを設定することができます。 チームでチャネルを使用することもできます。 (適用されていません)|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|着信呼び出しとのチャットは、Skype のビジネスにルーティングされます。|チームのみ|エンド ・ ユーザーが呼び出しを開始し、ビジネスしかし、唯一の Skype からチャットは、チームのミーティングをスケジュールします。 チームのチャネルの会話に参加できます。 (適用されていません)|
|TeamsOnly|着信呼び出しとのチャットは、チームに送られます|チームのみ|エンド ・ ユーザーには、呼び出しとチームからのチャットのみを開始できます。 ビジネス用の Skype には、ミーティングに参加するのにはできるだけです。|
|||||

**メモ:**

<sup>1</sup> PSTN の呼び出しの詳細については、このドキュメントの最後にある表を参照してください。

<sup>2</sup> SfBWithTeamsCollab と SfBWithTeamsCollabAndMeetings まだ公開されません管理者のユーザー エクスペリエンスで動作するため、現在 SfBOnly モードでは、Outlook のアドインを制御することを除いて、異なる。クライアント エクスペリエンスを提供すると後、これらのモードは管理ポータルで使用可能になります。 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: 移行と共存の管理

TeamsUpgradePolicy は、2 つのキー プロパティを公開する: モードと NotifySfbUsers。 
</br>
</br>

|パラメーター|種類|許容値</br>(イタリック体での既定値)|説明|
|---|---|---|---|
|モード|列挙型|*アイランド*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|クライアントを実行する必要がありますモードを示します。|
|NotifySfbUsers|ブール値|*False*または true|チームはビジネス用の Skype を交換してすぐにユーザーに通知するビジネス クライアント用の Skype のバナーを表示するかどうかを示します。 これは true を指定することはできない場合モード = TeamsOnly。|
|||||

チームでは、組み込み、読み取り専用のポリシーを使用して TeamsUpgradePolicy の関連するすべてのインスタンスを提供します。 したがって、のみを取得および許可のコマンドレットが利用できます。 組み込みのインスタンスは次のとおりです。
</br>
</br>

|ID |モード|NotifySfbUsers|
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
|グローバル</br>*既定*|アイランド|False|
||||

個々 のユーザーに、または、テナント全体では、これらのポリシーのインスタンスを与えることができます。 次に例を示します。
- チームには、ユーザー ($SipAddress) をアップグレードするには、"UpgradeToTeams"のインスタンスを与えます。</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 全体のテナントをアップグレードするには、grant コマンドの id パラメーターを省略します。</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>フェデレーションに関する考慮事項

チームからビジネス用の Skype を使用して別のユーザーのフェデレーションでは、ビジネスの Skype でオンライン チームのユーザーが所属する必要があります。 最終的のビジネス、オンプレミス ユーザーが Skype で所属チームは他のチームのユーザーとフェデレーションを行うことになります。

TeamsUpgradePolicy は、受信フェデレーション チャットと通話のルーティングを制御します。 フェデレーション ルーティングの動作は、*諸島モードで*は、同じテナントのシナリオの場合と同じです。  受信者は、島のモードでは。 
- チャットおよびチームから開始された呼び出しは、受信者が*フェデレーションのテナント*の場合はデバイスに着陸します。
- チャットおよびチームから開始された呼び出しは、受信者が*同じテナント*内にある場合はチームで着陸します。
- チャットと常にデバイスから開始された呼び出しは、デバイスで着陸します。


## <a name="the-intended-client-user-experience-in-teams-when-using-sfb-modes"></a>デバイスのモードを使用すると、チームで対象のクライアントのユーザーが発生します。

ユーザーは、Skype のビジネス ・ モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) のいずれかで、*チームのアプリケーションでの通話やチャット機能を無効にするものでは*、ですが、現在まだ無効でない場合。 同様と*を無効にするのには、チームでミーティングのスケジュール設定*をするには、SfBOnly または SfBWithTeamsCollab モードでは、ユーザーが、現在はありません。 自動的にこの経験を提供するソリューションを計画します。

まで、このソリューションを提供すると、管理者は TeamsMessagingPolicy、TeamsCallingPolicy、および TeamsMeetingPolicy の値を手動で構成する、対象のクライアントの経験、TeamsUpgradePolicy モードを適用できます。 さらを使用する場合`Grant-CsTeamsUpgradePolicy`PowerShell のコマンドレットが自動的にチェック determmine を TeamsMessagingPolicy、TeamsCallingPolicy、および TeamsMeetingPolicy に対応する設定の構成は、これらの設定と互換性がある場合指定したモードです。 いずれかが正しく構成されていません場合、は、補助金は成功しますが、どの設定が正しく構成されていないことを示す警告が提供されます。 管理者は、チームで互換性のあるエンド ユーザー エクスペリエンスを提供するのには示されているポリシーを更新する必要があります後。 管理者は、警告の結果としてのアクションは実行しませんが場合、ユーザー可能性があります、チャットへのアクセスを呼び出すと、または会議の TeamsMessagingPolicy、TeamsCallingPolicy、TeamsMeetingPolicy の値に応じてチームでのスケジュール設定機能エンド ユーザー エクスペリエンスに混乱する可能性があります。

### <a name="expected-values-of-workload-policy-settings-per-mode"></a>モードごとのポリシー設定の作業負荷の予測値
テーブルでは、TeamsUpgradeMode を付与するときにチェックされているポリシー設定を示します。 チーム内のチャンネルを無効にする SfBOnly モードの目的は、今後、します。ただしは現在の設定を無効にするチームで、チャネルの機能を可能にします。


|**モーダルかどうか (アプリケーション)**|**Policy.Setting**|
|---|---|
|チャット|TeamsMessagingPolicy.AllowUserChat|
|通話|TeamsCallingPolicy.AllowPrivateCalling|
|会議のスケジュール|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

次は、指定されたモードでは、これらの設定の値は。

|モード|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly または諸島|有効|有効|有効|有効|
|SfBWithTeamsCollabAndMeetings|無効|無効|有効|有効|
|SfBWithTeamsCollab または SfBOnly|無効|無効|無効|無効|
||||||


与える CsTeamsUpgradePolicy の中にこれらの設定の他の任意の組み合わせが検出された場合、付与成功しますが、正常な動作が準拠していない特定の設定を示す警告が表示されます。 一時的に、管理者する必要があります有効または無効に、中核となるワークロード ポリシーを使用して作業負荷。  TeamsUpgradePolicy に基づいての自動強制を実装すると、PowerShell の警告がクライアント エクスペリエンスを自動的に適用する管理者を通知するために更新されます。 その場合は、TeamsMessagingPolicy、TeamsCallingPolicy、および TeamsMeetingPolicy の値は変更されません-が、TeamsUpgradePolicy に従って、対象のクライアントの操作性が適用されます。

以下のようになりますが、PowerShell の警告の例に示します。


`PS C:\Users\janedoe> Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab
WARNING: The user 'user1@contoso.com' currently has effective policy enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the near term, when granting TeamsUpgradePolicy with mode=SfBWithTeamsCollab to a user, you must also separately assign policy to ensure the user has effective policy disabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the future, the capability will automatically honor TeamsUpgradePolicy.
PS C:\Users\janedoe>`


開始前に上記で説明したクライアントの動作の自動強制、デバイス モードの各動作が基本的に同じです。 SfBOnly、SfBWithTeamsCollab、および SfBWithTeamsCollabAndMeetings モードでは、チャットおよび着信呼び出しのルーティングにすべて同じです。 唯一の違いは、チームの Outlook アドインとビジネス用の Skype が有効になっているかどうかにします。 差別化されたクライアントのクライアントが配信されるまでは、管理ポータルで、デバイスのモードの 1 つだけが有効になります。 すべてのモードでは、PowerShell で使用できます。


## <a name="teamsinteroppolicy-and-legacy-mode-has-been-retired"></a>TeamsInteropPolicy とレガシー ・ モードが廃止されました。 

TeamsInteropPolicy は TeamsUpgradePolicy に置き換えられました。 以前に TeamsInteropPolicy を適用するすべてのコンポーネントは、代わりに TeamsUpgradePolicy を有効に更新されています。  マイクロソフトでは、TeamsInteropPolicy から TeamsUpgradePolicy への移行を容易にするために TeamsUpgradePolicy の「レガシー」モードが導入以前必要があります。 レガシー ・ モードで TeamsUpgradePolicy を理解するためのルーティング コンポーネントは、TeamsInteropPolicy に戻す元に戻します。 TeamsUpgradePolicy を完全にサポート ルーティングします。 レガシー ・ モードはサポートされていませんし、レガシー ・ モードを許可することは不要になった


## <a name="detailed-mode-descriptions"></a>詳細モードの説明
</br>
</br>

|モード|説明 (includeding は、クライアント エクスペリエンスを予定)|
|---|---|
|**アイランド**</br>(既定値)|ユーザーは、ビジネスとチーム サイド バイ サイドの両方の Skype を実行します。 次のユーザー:</br><ul><li>チャットを始めることができ、VOIP が企業やチームのクライアントのいずれかの Skype の呼び出しです。 注: ビジネス用の Skype でのユーザーのホーム サーバー受信者のモードに関係なく、ビジネス ユーザーを別の Skype に到達するチームから設置を開始できません。<li>チャットを受け取る & VOIP ビジネス クライアント用の Skype の他のユーザーがビジネスの開始で Skype を呼び出します。<li>チャットを受け取る & VOIP は、*同じテナント*内にある場合、チームのクライアントで別のユーザーで開始されるチームを呼び出します。<li>チャットを受け取る & VOIP を呼び出す別のユーザーで開始されたチーム、Skype のビジネス クライアントの*連合のテナント*内にある場合。 <li>次のように、PSTN の機能があります。<ul><li>設置型のビジネスで Skype ユーザーのホーム、PSTN の呼び出しが開始され、ビジネスの Skype で受信します。<li>ユーザーは、オンライン ホームでは、ユーザーが持っている電話システム ユーザーの場合。<ul><li>開始し、直接ルーティングするため、ユーザーが構成されている場合、チームで PSTN 通話を受信<li>開始し、ビジネス用の Skype で PSTN 通話を受信の場合、ユーザー、MS を呼び出すことを計画またはビジネス サーバー (ハイブリッド音声) のビジネス クラウド コネクタのエディションまたは Skype の設置型展開のいずれかの Skype 経由で PSTN ネットワークへの接続</ul></ul><li>チームやビジネス用の Skype で会議をスケジュールすることができます (と、既定では両方のプラグインを参照してください)。<li>任意の Skype ビジネスまたはチームの会議に参加できます。会議は、それぞれのクライアントに表示されます。</ul>|
|**SfBOnly**|ユーザーは、ビジネスの Skype のみを実行します。 次のユーザー:</br><ul><li>チャットおよびビジネス用の Skype からの呼び出しだけを実行できます。<li>コールを受信、チャット/ビジネスのクライアントに、Skype でに関係なく、開始、イニシエーターがビジネスのための Skype でのチームのユーザーでない限り、設置型のホームです。*<li>のビジネス会議、Skype のみをスケジュールすることができますが、Skype をビジネスまたはチームの会議に参加できます。</br> *、オンプレミスのユーザーとを使用する諸島モードが SfBOnly モードでは、他のユーザーとの組み合わせでお勧めしません。 設置型の呼び出し、または SfBOnly のユーザーとチャットを開始する場合は、ビジネスの Skype でのチームのユーザーのホーム、SfBOnly ユーザーが到達可能ではありませんし、失敗した呼び出しの email.* を受け取る|
|**SfBWithTeamsCollab**|ユーザーは、ビジネスとチーム サイド バイ サイドの両方の Skype を実行します。 次のユーザー:</br><ul><li>SfBOnly モードでユーザーの機能を持ちます。<li>グループ作業 (チャネル) に対してのみ有効にチームチャット、通話、または会議のスケジュールが無効になります。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|ユーザーは、ビジネスとチーム サイド バイ サイドの両方の Skype を実行します。 次のユーザー:<ul><li>SfBOnly モードでは、チャットとユーザーの呼び出し元の機能を持ちます。<li>グループのコラボレーションを有効にするチームである (チャンネル - チャネルの会話が含まれています)。チャットと通話を無効になります。<li>のみのチームのミーティングをスケジュールすることができますが、Skype をビジネスまたはチームの会議に参加できます。</ul>|
|**TeamsOnly**</br>(必要なデバイスのオンライン ホーム)|ユーザーは、チームだけを実行します。 次のユーザー:<ul><li>すべてのチャットを受信し、開始位置に関係なく、チームのクライアントで呼び出します。<li>チャットおよびチームからの呼び出しだけを実行できます。<li>のみ、チームでミーティングをスケジュールすることができますが、Skype をビジネスまたはチームの会議に参加できます。<li>ビジネス IP 電話の Skype を使用する続行できます。</ul> |
|||




## <a name="related-topics"></a>関連トピック

[Skype for Business と共存する](https://docs.microsoft.com/en-us/microsoftteams/coexistence-chat-calls-presence)

[Get CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[許可 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[セット CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)


