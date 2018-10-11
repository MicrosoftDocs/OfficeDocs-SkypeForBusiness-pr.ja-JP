---
title: ビジネスのチームとは、Skype を使用する組織の移行と相互運用性のガイド
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: チームにビジネス用の Skype からの移行を管理するためのガイダンス
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd12b4e5f054d3410f1e62e7ed09476ffac6754b
ms.sourcegitcommit: 08933c8f795048feaa05828e000df5082ac90761
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "25495607"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>ビジネスのチームとは、Skype を使用する組織の移行と相互運用性のガイド

相互運用と移行は、「共存モード」を使用して TeamsUpgradePolicy によって管理されます。 ユーザーのモードの選択では、着信呼び出しとチャット、およびユーザーがチームやビジネス用の Skype で会議をスケジュールするかどうかの両方のルーティングを制御します。  すぐに、今後の TeamsAppPermissionsPolicy と協力して、モードも、どのクライアントでユーザーがチャットや通話を開始できます。 

2018年 4 月ですでに発表済みと TeamsInteropPolicy は現在使用します。 機能は、TeamsUpgradePolicy に統合されているし、TeamsInteropPolicy を構成する必要はなくなりました。 それが無効になる TeamsUpgradePolicy モードがある場合を除き、レガシを = します。  現在表示されている TeamsUpgradePolicy のサポートは、*ユーザーがレガシ以外のモードを使用するには、その構成を更新する必要があります*。 モードでは TeamsUpgradePolicy のインスタンスを与える = レガシーが既定でブロックされるようになりました。

## <a name="fundamental-concepts"></a>基本的な概念

1.  *相互運用機能*: ビジネス ・ ユーザーの Lync と Skype とチームのユーザーの間で 1 対 1 の通信です。

2.  *フェデレーション*: ユーザーが別のテナントの間の通信します。

3.  すべてのビジネス アカウントを「ホーム」いずれかのオンラインのユーザーが、基になる Skype をあるチームまたは設置。
    - 既に Skype を使用してオンライン ビジネスのユーザーは、既存のオンライン アカウントを使用します。
    - 既に Skype を使用する設置型のビジネスと Lync ユーザーは、既存のオンプレミス アカウントを使用します。
    - ユーザーが対象となる、既存の Skype のビジネス アカウントを検出できませんが、Skype のオンライン ビジネスのアカウント チームのユーザーが作成されるときに自動的に準備があります。 Skype ビジネス ライセンスが必要ではありません。

4.  ビジネスまたは Lync では、いずれかの Skype の設置型展開があるし、それらのユーザーのチームのユーザーに、最低限、必ず Azure AD 接続が msRTCSIP-DeploymentLocator を同期しているビジネスのチームと Skype は、そのために AAD、属性オンライン、オンプレミス環境を正しく検出します。 さらに、チーム専用のモードを任意のユーザーを移動する (つまり、アップグレード、ユーザー)、 *Skype のビジネスのハイブリッド モードを構成する必要があります*。

5.  ビジネス ユーザーのチームと Skype との間の相互運用機能は、使用可能な*ビジネス用の Skype でチームのユーザーは、オンライン ホーム サーバーの場合*だけです。 Skype ビジネス ユーザーが所属することができますか、オンプレミス (とビジネスのハイブリッドの Skype を設定する必要があります) の受信者またはオンラインです。 設置型のビジネスが Skype に置かれているユーザーは、(このドキュメントの後半で定義)、島のモードでチームを使用することができますが、チームを使用して、相互運用機能またはビジネスの Skype を使用して他のユーザーとフェデレーションを行うことはできません。  

6.  チームにユーザーをアップグレードするのには (モードでは TeamsUpgradePolicy を付与、つまり = TeamsOnly)、ビジネスの Skype のオンライン ユーザーのホーム必要があります。 これは、相互運用性、フェデレーション、およびチームのユーザーの完全な管理を確実に必要です。 ホーム設置型であるユーザーをアップグレードするのにを使用して、 `Move-CsUser` 、設置から管理用ツールの最初の移動に Skype ユーザーは、オンライン ビジネス。

    - Skype ビジネス サーバー 2019 または CU8 の Skype のビジネス サーバー 2015 の指定の`-MoveToTeams`でスイッチを`Move-CsUser`のチームに直接ユーザーを移動します。
    - それ以外の場合後、`Move-CsUser`が完了したら、PowerShell またはチームの管理センターを使用してそのユーザーに TeamsOnly モードを割り当てます。 

7.  アップグレードと相互運用機能を管理するための中核となるポリシーは、TeamsUpgradePolicy です。 TeamsInteropPolicy は TeamsUpgradePolicy モードを使用するとき以外は受け入れられる不要になった = レガシー、およびモードを使用して顧客 = レガシーの別のモードを使用する TeamsUpgradePolicy の構成を更新する必要があります。  許可モード = 管理者がこのメソッドをオーバーライドを使用していますが、既定では、レガシがブロックされました`-Force`されています。 最終的に、`-Force`スイッチを削除し、許可を与えるモードとなります = レガシを実行できなくなります。 

8.  チームとチームの電話システムの機能を使用するユーザーは TeamsOnly モード (すなわち、Skype でオンライン ビジネスのホームをアップグレードしてチーム) である必要があり、マイクロソフトの電話システムに[直接ルーティングの場合](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277)(これは電話システムを使用できるように構成する必要がありますか独自の SIP トランクおよび SBC を使用して) を持つことも、Office 365 を呼び出すことを計画します。   

9.  オーディオ会議でチームのミーティングのスケジュール (ダイヤルインまたはダイヤルアウトを PSTN 経由で) は、オンライン ビジネスの Skype をホームとしているユーザーにのみ現在利用可能です。 オンプレミス Skype のビジネス アカウントでチームのユーザーのサポートは、タップでは。


## <a name="coexistence-modes"></a>共存モード

相互運用と移行はこれで TeamsUpgradePolicy を使用して「共存モード」に基づき管理されます。 ユーザーのモードを決定します。

- *着信ルーティング*: クライアント (チームやビジネス用の Skype) は、どの着信チャットで着陸を呼び出しますか? 
- *会議のスケジュール設定*: 新しい会議をスケジュールしたり、適切なアドインが存在する Outlook でどのサービスを使用します。 TeamsUpgradePolicy では、会議の参加は制御されませんに注意してください。 ユーザーが常に*結合*すべての会議では、ビジネス会議やチーム会議、Skype であるかどうか。
- *クライアントで発生する*: どのような機能は、ビジネス クライアントのチームや Skype で利用できるでしょうか。 これは TeamsOnly モードを実装します。 他のモードのサポートは、今後の TeamsAppPermissionsPolicy に依存します。 この新しいポリシーが適用されて、TeamsUpgradePolicy はチームが必要なモードを正しく構成されていることを確認することで、依存関係にがあります。

計画モードは次のとおりです。 SfBWithTeamsCollab と SfBWithTeamsCollabAndMeetings は、重複機能を持つが、両方のクライアントの混在の使用をことができません。 アイランド モードでは、機能が重複しているのですが、両方のクライアントの使用の状況を許可します。 たとえば、諸島モードでは、ユーザーはビジネスやチームのいずれかの Skype でチャットを開始する可能性がありますが、SfBWithTeamsCollab、ビジネスの Skype のことができますチャットのみです。 すべてのモードがまだ完全に使用可能に注意してください。  
</br>
</br>

|モード|ルーティング動作|会議のスケジュール|クライアント エクスペリエンス|
|---|---|---|---|
|諸島|VOIP の着信呼び出し、受信者の連合と島のモードで以外と発信者、同じクライアントでの着陸のチャット デバイス。<sup>1</sup>で着陸する場合に|両方|エンド ・ ユーザーは、呼び出しと、クライアントでは、チャットを開始できるし、クライアントの会議をスケジュールすることができます。|
|SfBOnly|着信呼び出しとのチャットは、Skype のビジネスにルーティングされます。|Skype ビジネスだけに|エンド ・ ユーザーでは、呼び出しとのみ、ビジネスの Skype のチャットを開始でき、のみ Skype のビジネス ・ ミーティングのスケジュールを設定することができます。 (適用されていません)|
|SfBWithTeamsCollab<sup>2</sup>|着信呼び出しとのチャットは、Skype のビジネスにルーティングされます。|Skype ビジネスだけに|エンド ・ ユーザーでは、呼び出しとのみ、ビジネスの Skype のチャットを開始でき、のみ Skype のビジネス ・ ミーティングのスケジュールを設定することができます。 チームでチャネルを使用することもできます。 (適用されていません)|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|着信呼び出しとのチャットは、Skype のビジネスにルーティングされます。|チームのみ|エンド ・ ユーザーが呼び出しを開始し、ビジネスしかし、唯一の Skype からチャットは、チームのミーティングをスケジュールします。 チームでチャネルを使用することもできます。 (適用されていません)|
|TeamsOnly|着信呼び出しとのチャットは、チームに送られます|チームのみ|エンド ・ ユーザーには、呼び出しとチームからのチャットのみを開始できます。 ビジネス用の Skype には、ミーティングに参加するのにはできるだけです。|
|レガシー</br>*非推奨*|TeamsInteropPolicy に基づくルーティング|影響なし|影響はありません。 TeamsInteropPolicy から TeamsUpgradePolicy への移行を円滑化する一時的なモードでした。 TeamsUpgradePolicy が完全にサポートされているため、*お客様は、レガシー以外のモードを構成を更新する必要があります*。  レガシー ・ モードの許可は既定でブロックされるようになりました。 |
|||||

**メモ:**

<sup>1</sup> PSTN の呼び出しの詳細については、このドキュメントの最後にある表を参照してください。

<sup>2</sup> SfBWithTeamsCollab と SfBWithTeamsCollabAndMeetings、まだ公開されません管理者のユーザー エクスペリエンスの動作するため、現在 no SfBOnly モードとは異なる。 クライアント エクスペリエンスを提供すると後、は、これらのモードが表示されます。 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: 移行と共存の管理

TeamsUpgradePolicy は、3 つのプロパティを公開します。 主プロパティは、モードと NotifySfbUsers です。 アクション従来のパラメーターは、モードと NotifySfbUsers の組み合わせを完全に冗長化されました。
</br>
</br>

|パラメーター|種類|許容値</br>(イタリック体での既定値)|説明|
|---|---|---|---|
|モード|列挙型|*諸島*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>レガシー|クライアントを実行する必要がありますモードを示します。 場合モード = レガシでは、このポリシーを使用するコンポーネントは、TeamsInteropPolicy に従うことに戻されます。 TeamsUpgradePolicy が完全にサポートされていますし、ユーザーがレガシ以外の構成の使用モードを更新する必要があります。|
|NotifySfbUsers|ブール値|*False*または true|チームはビジネス用の Skype を交換してすぐにユーザーに通知するビジネス クライアント用の Skype のバナーを表示するかどうかを示します。 これは true を指定することはできない場合モード = TeamsOnly。|
|アクション</br>*非推奨*|列挙型|*なし*、アップグレードを通知します。|これは、冗長モードと NotifySfbUsers の組み合わせであるために、最終的には削除され、従来のパラメーターです。 |
|||||

チームでは、組み込み、読み取り専用のポリシーを使用して TeamsUpgradePolicy の関連するすべてのインスタンスを提供します。 したがって、のみを取得および許可のコマンドレットが利用できます。 組み込みのインスタンスは次のとおりです。
</br>
</br>

|ID |モード|NotifySfbUsers|アクション|コメント|
|---|---|---|---|---|
|諸島|諸島|False|なし||
|IslandsWithNotify|諸島|True|通知||
|SfBOnly|SfBOnly|False|なし|ここでは、このモードは、効果的に推奨されるクライアントの設定と同じデバイスを = します。 予想、将来的にこのチームの機能が制限されます。|
|SfBOnlyWithNotify|SfBOnly|True|通知|ここでは、このモードは、効果的に推奨されるクライアントの設定と同じデバイスを = します。 予想、将来的にこのチームの機能が制限されます。|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|なし|このモードでは、PowerShell のレイヤーに存在するが、管理者のユーザー エクスペリエンスでは、まだ公開されていません。 ルーティングの観点から、これは SfBOnly モードと同じです。 チームのアプリケーションでチャンネルは TeamsAppPolicy を使用するとこれだけ許可されます。|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|通知|このモードでは、PowerShell のレイヤーに存在するが、管理者のユーザー エクスペリエンスでは、まだ公開されていません。 ルーティングの観点から、これは SfBOnly モードと同じです。 チームのアプリケーションでチャンネルは TeamsAppPolicy を使用するとこれだけ許可されます。|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|なし|このモードでは、PowerShell のレイヤーに存在するが、管理者のユーザー エクスペリエンスでは、まだ公開されていません。 ルーティングの観点から、これは SfBOnly モードと同じです。 TeamsAppPolicy の利用可能な場合、これで、チャネル、およびチームの会議。|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|通知|このモードでは、PowerShell のレイヤーに存在するが、管理者のユーザー エクスペリエンスでは、まだ公開されていません。 ルーティングの観点から、これは SfBOnly モードと同じです。 TeamsAppPolicy の利用可能な場合、これで、チャネル、およびチームの会議。|
|UpgradeToTeams|TeamsOnly|False|Upgrade|チームにユーザーをアップグレードして、チャット、通話、およびビジネスのための Skype で会議のスケジュール設定をしないようにするのには、このモードを使用します。|
|グローバル|レガシー|False|なし|モードは、島に、近い将来に更新されます。|
|NoUpgrade|レガシー|False|なし|このインスタンスを破棄することがすぐにされます。|
|NotifyForTeams|レガシー|True|通知|このインスタンスを破棄することがすぐにされます。|
||||||

個々 のユーザーに、または、テナント全体では、これらのポリシーのインスタンスを与えることができます。 例:
- チームには、ユーザー ($SipAddress) をアップグレードするには、"UpgradeToTeams"のインスタンスを与えます。</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 全体のテナントをアップグレードするには、grant コマンドの id パラメーターを省略します。</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`



## <a name="teamsinteroppolicy-and-legacy-mode-being-retired"></a>TeamsInteropPolicy と廃止されているレガシー ・ モード 

前述のように、TeamsUpgradePolicy、TeamsInteropPolicy は交換済み。 以前に TeamsInteropPolicy を適用するすべてのコンポーネントは、代わりに TeamsUpgradePolicy を有効に更新されています。 

マイクロソフトでは、以前 TeamsInteropPolicy から TeamsUpgradePolicy への移行を容易にするために TeamsUpgradePolicy の「レガシー」モードを導入しました。 レガシー ・ モードで TeamsUpgradePolicy を理解するためのルーティング コンポーネントは、TeamsInteropPolicy に戻す元に戻します。 TeamsUpgradePolicy を完全にサポートのルーティングおよびレガシー ・ モードを使用する必要性は不要です。 *レガシー ・ モードを使用しているお客様の他のモードのいずれかを使用するのには TeamsUpgradePolicy の構成を更新する必要があります。* 

レガシー ・ モードを使用してお客様は、TeamsInteropPolicy は以下の 3 つの特定インスタンスのみがサポートされていることが通知されます。 どちらの場合も、CallingDefaultClient の値には、ChatDefaultClient の値が一致して AllowEndUserClientOverride は常に false です。 
</br>
</br>
**TeamsUpgradePolicy モードを使用する場合は、TeamsInteropPolicy のインスタンスをサポートされているレガシの =**
</br>
</br>

|ID |AllowEndUserClientOverride|CallingDefaultClient|ChatDefaultClient|
|---|---|---|---|
|`DisallowOverrideCallingDefaultChatDefault`|False|既定|既定|
|`DisallowOverrideCallingSfbChatSfb`|False|デバイス|デバイス|
|`DisallowOverrideCallingTeamsChatTeams`|False|Teams|Teams|
|||||

$Policy が上記の id の値のいずれか、次のコマンドレットの構文を使用します。`Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

## <a name="federation-considerations"></a>フェデレーションに関する考慮事項

チームからビジネス用の Skype を使用して別のユーザーのフェデレーションでは、ビジネスの Skype でオンライン チームのユーザーが所属する必要があります。 最終的のビジネス、オンプレミス ユーザーが Skype で所属チームは他のチームのユーザーとフェデレーションを行うことになります。

TeamsUpgradePolicy は、受信フェデレーション チャットと通話のルーティングを制御します。 フェデレーション ルーティングの動作は、*諸島モードで*は、同じテナントのシナリオの場合と同じです。  受信者は、島のモードでは。 
- チャットおよびチームから開始された呼び出しは、受信者が*フェデレーションのテナント*の場合はデバイスに着陸します。
- チャットおよびチームから開始された呼び出しは、受信者が*同じテナント*内にある場合はチームで着陸します。
- チャットと常にデバイスから開始された呼び出しは、デバイスで着陸します。


## <a name="completing-the-transition-to-mode-management"></a>モードの管理への移行を完了します。

今年の後半、マイクロソフトは、新しいポリシーの種類、TeamsAppPermissionsPolicy、IM、会議、チャット チャンネル) などのチームのクライアントには、どの部分が有効になっているかを制御するために導入する予定です。 チームでの作業負荷を有効または無効にする新しいポリシーが利用可能になったら、TeamsUpgradePolicy が更新され、TeamsAppPolicy が適切であることを確認するのにはチェックが最初に管理者が TeamsUpgradePolicy のインスタンスをユーザーに許可しようとすると、ご希望のモードを構成します。 それ以外の場合は、補助金は、他のポリシーする必要があります最初の設定方法を説明するエラーで失敗します。 

TeamsAppPolicy が使用可能になるまで基本的には TeamsUpgradePolicy が呼び出しとチャットなどと同様の会議のスケジュール設定 (Outlook アドインで公開されている) とルーティングを制御します。 チームのクライアントの動作ではないためまだ場所には、現代のポータルのすべてのモードが有効になります。 ルーティングの観点から、SfBOnly、SfBWithTeamsCollab、および SfBWithTeamsCollabAndMeetings モードと同じです。 

## <a name="action-required-for-organizations-that-were-using-teamsinteroppolicy"></a>TeamsInteropPolicy を使用している組織に必要なアクション

TeamsInteropPolicy を使用しているお客様。 
1. TeamsInteropPolicy を持つユーザーが割り当てられているこれら 3 つの組み込みインスタンスの 1 つだけ、CallingDefaultClient のことを確認 = ChatDefaultClient、およびどの AllowEndUserClientOverride = false です。 これらのインスタンスは次のとおりです。
   </br>
   </br>

   |ID |AllowEndUserClientOverride |CallingDefaultClient|ChatDefaultClient|
   |---|---|---|---|
   |`DisallowOverrideCallingDefaultChatDefault`|False|既定|既定|
   |`DisallowOverrideCallingSfbChatSfb`|False|デバイス|デバイス|
   |`DisallowOverrideCallingTeamsChatTeams`|False|Teams|Teams|
   |||||

    $Policy が上記の id の値のいずれか、次のコマンドレットの構文を使用します。

    `Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

    **マイクロソフトでは、お客様が、2018 年 6 月 30 日で、ポリシーを更新することを要求します。** いずれかの時点以降は、マイクロソフトは削除 TeamsInteropPolicy の他のインスタンスです。</br> 
    ***これらのインスタンスのいずれかに更新しないとしている組織は、これらのインスタンスのいずれかに自動的に更新され、ユーザーを最終的にがあります。明らかが希望されるお客様は、ユーザーにとっては最善を選択することができますように。***

2. 組み込みのグローバル ポリシーをカスタマイズする場合、これを元に戻します。 グローバルのポリシーは、次の値が必要です。
   </br>
   </br>

    |パラメーター|値|
    |---|---|
    |`AllowEndUserClientOverride`|False|
    |`CallingDefaultClient`|既定|
    |`ChatDefaultClient`|既定|
    |||

    上記と異なる値のいずれかの場合は、すべてのテナントに固有のカスタマイズを削除するのには、次を実行します。

    `Grant-CsTeamsInteropPolicy -PolicyName $null`




## <a name="action-required-for-organizations-that-are-using-modelegacy"></a>必要な操作モードを使用している組織にとって、レガシーを =

モードを使用しているお客様 = TeamsUpgradePolicy で (ポリシー インスタンスは NoUpgrade またはポリシーのインスタンスを = = NotifyForTeams) レガシー以外のモードでポリシーを使用するには、その構成を更新する必要があります。 

 **マイクロソフトでは、お客様が、2018 年 11 月 15 日で、レガシー ・ モードのすべての使用を削除することを要求します。** いずれかの時点以降は、マイクロソフトは、のインスタンスを削除 TeamsUpgradePolicy モードではレガシーを = します。</br> 


## <a name="detailed-mode-descriptions"></a>詳細モードの説明
</br>
</br>

|モード|解説|
|---|---|
|**諸島**</br>(既定値)|1 人のユーザーは、ビジネスとチーム サイド バイ サイドの両方の Skype を実行します。 次のユーザー:</br><ul><li>チャットを始めることができ、VOIP が企業やチームのクライアントのいずれかの Skype の呼び出しです。 注: ビジネス用の Skype でのユーザーのホーム サーバー別の Skype のビジネス ユーザーに到達するチームから設置を開始できません。<li>チャットとビジネス クライアント用の Skype の他のユーザーで Skype のビジネスを開始する VOIP 通話を受信します。<li>チャットと*同じテナント*内にある場合に、チームで、チームのクライアントで別のユーザーによって開始された VOIP 通話を受信します。<li>チャットと ina*連合のテナント*である場合に、チームでビジネス クライアント用の Skype の他のユーザーによって開始された VOIP 呼び出しを受信します。 <li>次のように、PSTN の機能があります。<ul><li>設置型のビジネスで Skype ユーザーのホーム、PSTN の呼び出しが開始され、ビジネスの Skype で受信します。<li>ユーザーは、オンライン ホームでは、ユーザーが持っている電話システム ユーザーの場合。<ul><li>開始し、直接ルーティングするため、ユーザーが構成されている場合、チームで PSTN 通話を受信<li>開始し、ビジネス用の Skype で PSTN 通話を受信の場合、ユーザー、MS を呼び出すことを計画またはビジネス サーバー (ハイブリッド音声) のビジネス クラウド コネクタのエディションまたは Skype の設置型展開のいずれかの Skype 経由で PSTN ネットワークへの接続</ul></ul><li>チームやビジネス用の Skype で会議をスケジュールすることができます (と、既定では両方のプラグインを参照してください)。<li>任意の Skype ビジネスまたはチームの会議に参加できます。会議は、それぞれのクライアントに表示されます。</ul>|
|**SfBOnly**|1 人のユーザーには、ビジネスの Skype のみが実行されます。 次のユーザー:</br><ul><li>チャットおよびビジネス用の Skype からの呼び出しだけを実行できます。<li>コールを受信、チャット/ビジネスのクライアントに、Skype でに関係なく、開始、イニシエーターがビジネスのための Skype でのチームのユーザーでない限り、設置型のホームです。*<li>のビジネス会議、Skype のみをスケジュールすることができますが、Skype をビジネスまたはチームの会議に参加できます。</br> *、オンプレミスのユーザーとを使用する諸島モードが SfBOnly モードでは、他のユーザーとの組み合わせでお勧めしません。 設置型の呼び出し、または SfBOnly のユーザーとチャットを開始する場合は、ビジネスの Skype でのチームのユーザーのホーム、SfBOnly ユーザーが到達可能ではありませんし、失敗した呼び出しの email.* を受け取る|
|**SfBWithTeamsCollab**|1 人のユーザーは、ビジネスとチーム サイド バイ サイドの両方の Skype を実行します。 次のユーザー:</br><ul><li>SfBOnly モードでユーザーの機能を持ちます。<li>グループ作業 (チャネル) に対してのみ有効にチームチャット、通話、または会議のスケジュールが無効になります。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|1 人のユーザーは、ビジネスとチーム サイド バイ サイドの両方の Skype を実行します。 次のユーザー:<ul><li>SfBOnly モードでは、チャットとユーザーの呼び出し元の機能を持ちます。<li>チーム グループ コラボレーション対応 (チャネル)。チャットと通話を無効になります。<li>のみのチームのミーティングをスケジュールすることができますが、Skype をビジネスまたはチームの会議に参加できます。</ul>|
|**TeamsOnly**</br>(必要なデバイスのオンライン ホーム)|1 人のユーザーには、チームだけが実行されます。 次のユーザー:<ul><li>すべてのチャットを受信し、開始位置に関係なく、チームのクライアントで呼び出します。<li>チャットおよびチームからの呼び出しだけを実行できます。<li>のみ、チームでミーティングをスケジュールすることができますが、Skype をビジネスまたはチームの会議に参加できます。<li>ビジネス IP 電話の Skype を使用する続行できます。</ul> |
|**レガシー**</br>(非推奨)|このモードは、ソフトウェアと一貫性のあるエクスペリエンスを TeamsInteropPolicy TeamsUpgradePolicy への移行中に使用された変更内容を公開します。このモードは、不要になった TeamsUpgradePolicy が完全にサポートされているようになりました。 モードを使用して顧客 = レガシが別のモードで使用するには、その構成を更新する必要があります。|
|||




## <a name="related-topics"></a>関連トピック

[Get CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[許可 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsinteroppolicy?view=skype-ps)

[許可 CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsinteroppolicy?view=skype-ps)

[削除 CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsinteroppolicy?view=skype-ps)

[Get CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[新しい-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsupgradepolicy?view=skype-ps)

[削除 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsupgradepolicy?view=skype-ps)

[セット CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[セット CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradepolicy?view=skype-ps)
