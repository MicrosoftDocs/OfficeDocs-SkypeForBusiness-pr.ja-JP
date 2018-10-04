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
ms.openlocfilehash: 16a10f73614626a422bf6b869d08c4019982d0d2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375894"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>ビジネスのチームとは、Skype を使用する組織の移行と相互運用性のガイド

2018 年 4 月では、マイクロソフトからの移行チームに Skype ビジネスとどのようにこれら 2 つのクライアントが共存可能特定のユーザーのためのガイダンスを明示しました。 その時点では、管理の合理化し、エンド ・ ユーザーの満足度の向上に計画的な変更を発表しました。 以来、マイクロソフトは、その計画の一貫性のある管理者のユーザー エクスペリエンスでは、更新プログラムを配信しました。 このドキュメントでは説明には、それらの変更が反映されます。

発表前に、TeamsInteropPolicy が廃止されています。 機能は、TeamsUpgradePolicy に統合されています。 相互運用と移行は、「共存モード」を使用して TeamsUpgradePolicy によって管理されます。 ユーザーのモードの選択では、着信呼び出しとチャット、およびユーザーがチームやビジネス用の Skype で会議をスケジュールするかどうかの両方のルーティングを制御します。  すぐに、今後の TeamsAppPermissionsPolicy と協力して、モードも、どのクライアントでユーザーがチャットや通話を開始できます。 

TeamsInteropPolicy を構成する必要はなくなりました。 それが無効になる TeamsUpgradePolicy モードがある場合を除き、レガシを = します。  TeamsUpgradePolicy のサポートが完了したのでユーザーは、レガシー以外のモードを使用するには、その構成を更新する必要があります。 モードでは TeamsUpgradePolicy のインスタンスを与える = レガシーが既定でブロックされるようになりました。

## <a name="fundamental-concepts"></a>基本的な概念

1.  *相互運用機能*: ビジネス ・ ユーザーの Lync と Skype とチームのユーザーの間で 1 対 1 の通信です。

2.  *フェデレーション*: ユーザーが別のテナントの間の通信します。

3.  すべてのビジネス アカウントを「ホーム」いずれかのオンラインのユーザーが、基になる Skype をあるチームまたは設置。
    - 既に Skype を使用してオンライン ビジネスのユーザーは、既存のオンライン アカウントを使用します。
    - 既に Skype を使用する設置型のビジネスと Lync ユーザーは、既存のオンプレミス アカウントを使用します。
    - ユーザーが対象となる、既存の Skype のビジネス アカウントを検出できませんが、Skype のオンライン ビジネスのアカウント チームのユーザーが作成されるときに自動的に準備があります。 Skype ビジネス ライセンスが必要ではありません。

4.  ビジネスまたは Lync では、いずれかの Skype の設置型展開があるし、それらのユーザーのチームのユーザーに、最低限、必ず Azure AD 接続が msRTCSIP-DeploymentLocator を同期しているビジネスのチームと Skype は、そのために AAD、属性オンライン、オンプレミス環境を正しく検出します。 さらに、チーム専用のモードを任意のユーザーを移動する (つまり、アップグレード、ユーザー)、 *Skype のビジネスのハイブリッド モードを構成する必要があります*。

5.  ビジネス ユーザーのチームと Skype との間の相互運用機能は、使用可能な*ビジネス用の Skype でチームのユーザーは、オンライン ホーム サーバーの場合*だけです。 Skype ビジネス ユーザーが所属することができますか、オンプレミス (と Skype をビジネスのハイブリッドの設定が必要です) またはオンラインです。 設置型のビジネスが Skype に置かれているユーザーは、(このドキュメントの後半で定義)、島のモードでチームを使用することができますが、チームを使用して、相互運用機能またはビジネスの Skype を使用して他のユーザーとフェデレーションを行うことはできません。  

6.  チームにユーザーをアップグレードするのには (モードでは TeamsUpgradePolicy を付与、つまり = TeamsOnly)、ビジネスの Skype のオンライン ユーザーのホーム必要があります。 これは、相互運用性、フェデレーション、およびチームのユーザーの完全な管理を確実に必要です。 ホーム設置型であるユーザーをアップグレードするのにを使用して、 `Move-CsUser` 、設置から管理用ツールの最初の移動に Skype ユーザーは、オンライン ビジネスです。 次 TeamsUpgradePolicy と TeamsInteropPolicy をオンラインのユーザーに付与または TeamsOnly モードを割り当てるには、現代のポータルを使用します。 1 回ビジネス サーバー 2015 船の Skype の CU8、顧客だけで使用して、新しい`-MoveToTeams`でスイッチを`Move-CsUser`1 に 2 つの手順を結合します。

7.  アップグレードと相互運用機能を管理するための中核となるポリシーは、TeamsUpgradePolicy です。 TeamsInteropPolicy は TeamsUpgradePolicy モードを使用するとき以外は使用されなく = レガシー、およびモードを使用して顧客 = レガシーの別のモードを使用する TeamsUpgradePolicy の構成を更新する必要があります。  許可モード = 管理者がこのメソッドをオーバーライドを使用していますが、既定では、レガシがブロックされました`-Force`されています。 最終的に、`-Force`スイッチを削除し、許可を与えるモードとなります = レガシを実行できなくなります。 

8.  チームの電話システムを使用する機能、ユーザーが TeamsOnly モード (すなわち、Skype でオンライン ビジネスのホームをアップグレードしてチーム) である必要がありますおよびマイクロソフトの電話システムが[直接ルーティング](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277)を構成する必要がありますか (電話システムを使用できるようにする、SIP トランクおよび SBC を所有する) ことも、Office 365 を呼び出すことを計画します。   

9.  オーディオ会議でチームのミーティングのスケジュール (ダイヤルインまたはダイヤルアウトを PSTN 経由で) は、オンライン ビジネスの Skype をホームとしているユーザーにのみ現在利用可能です。 オンプレミス Skype のビジネス アカウントでチームのユーザーのサポートは、タップでは。


## <a name="coexistence-modes"></a>共存モード

管理の合理化とエンド ・ ユーザーの満足度を高め、相互運用と移行管理されていますが TeamsUpgradePolicy を使用して「共存モード」にします。 ユーザーのモードを決定します。

- *着信ルーティング*: クライアント (チームやビジネス用の Skype) は、どの着信チャットで着陸を呼び出しますか? 
- *会議のスケジュール設定*: 新しい会議をスケジュールしたり、適切なアドインが存在する Outlook でどのサービスを使用します。 TeamsUpgradePolicy では、会議の参加は制御されませんに注意してください。 ユーザーが常に*結合*すべての会議では、ビジネス会議やチーム会議、Skype であるかどうか。
- *クライアントで発生する*: どのような機能は、ビジネス クライアントのチームや Skype で利用できるでしょうか。 これは TeamsOnly モードを実装します。 他のモードのサポートは、今後の TeamsAppPermissionsPolicy に依存します。 この新しいポリシーが適用されて、TeamsUpgradePolicy はチームが必要なモードを正しく構成されていることを確認することで、依存関係にがあります。

計画モードは次のとおりです。 SfBWithTeamsCollab と SfBWithTeamsCollabAndMeetings は、重複機能を持つが、両方のクライアントの混在の使用をことができません。 アイランド モードでは、機能が重複しているのですが、両方のクライアントの使用の状況を許可します。 たとえば、諸島モードでは、ユーザーはビジネスやチームのいずれかの Skype でチャットを開始する可能性がありますが、SfBWithTeamsCollab、ビジネスの Skype のことができますチャットのみです。 すべてのモードがまだ完全に使用可能に注意してください。  
</br>
</br>

|モード|ルーティング動作|会議のスケジュール|クライアント エクスペリエンス|
|---|---|---|---|
|諸島|着信 VOIP を呼び出し、開始者<sup>1</sup>と同じクライアントでの着陸のチャット|両方|エンド ・ ユーザーは、呼び出しと、クライアントでは、チャットを開始できるし、クライアントの会議をスケジュールすることができます。|
|SfBOnly|着信呼び出しとのチャットは、Skype のビジネスにルーティングされます。|Skype ビジネスだけに|エンド ・ ユーザーでは、呼び出しとのみ、ビジネスの Skype のチャットを開始でき、のみ Skype のビジネス ・ ミーティングのスケジュールを設定することができます。 (適用されていません)|
|SfBWithTeamsCollab<sup>2</sup>|着信呼び出しとのチャットは、Skype のビジネスにルーティングされます。|Skype ビジネスだけに|エンド ・ ユーザーでは、呼び出しとのみ、ビジネスの Skype のチャットを開始でき、のみ Skype のビジネス ・ ミーティングのスケジュールを設定することができます。 チームでチャネルを使用することもできます。 (適用されていません)|
|SfBWithTeamsCollabAndMeetings<sup>3</sup>|着信呼び出しとのチャットは、Skype のビジネスにルーティングされます。|チームのみ|エンド ・ ユーザーが呼び出しを開始し、ビジネスしかし、唯一の Skype からチャットは、チームのミーティングをスケジュールします。 チームでチャネルを使用することもできます。 (適用されていません)|
|TeamsOnly|着信呼び出しとのチャットは、チームに送られます|チームのみ|エンド ・ ユーザーには、呼び出しとチームからのチャットのみを開始できます。 ビジネス用の Skype には、ミーティングに参加するのにはできるだけです。|
|レガシー|TeamsInteropPolicy に基づくルーティング|影響なし|影響はありません。 TeamsInteropPolicy から TeamsUpgradePolicy への移行を円滑化する一時的なモードでした。 お客様がもはやこのモードを使用する必要があり、レガシー以外のモードには、構成を更新する必要がありますので、TeamsUpgradePolicy が完全にサポートされています。 |
|||||

**メモ:**

<sup>1</sup> PSTN の呼び出しの詳細については、このドキュメントの最後にある表を参照してください。

<sup>2</sup> SfBWithTeamsCollab はまだ公開されません管理者のユーザー エクスペリエンスのため、現在の動作モードの SfBOnly を区別なく。 クライアント エクスペリエンスが配信されると、このモードが表示されます。

<sup>3</sup> SfBWithTeamsCollabAndMeetings はまだ使用できません。 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: 移行と共存の管理

TeamsUpgradePolicy は、3 つのプロパティを公開します。 主プロパティは、モードと NotifySfbUsers です。 アクション従来のパラメーターは、モードと NotifySfbUsers の組み合わせを完全に冗長化されました。
</br>
</br>

|パラメーター|種類|許容値</br>(イタリック体での既定値)|説明|
|---|---|---|---|
|モード|列挙型|*諸島*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>レガシー|クライアントを実行する必要がありますモードを示します。 場合モード = レガシでは、このポリシーを使用するコンポーネントは、TeamsInteropPolicy に従うことに戻されます。 TeamsUpgradePolicy が完全にサポートされていますし、ユーザーがレガシ以外の構成の使用モードを更新する必要があります。|
|NotifySfbUsers|ブール値|*False*または true|チームはビジネス用の Skype を交換してすぐにユーザーに通知するビジネス クライアント用の Skype のバナーを表示するかどうかを示します。 これは true を指定することはできない場合モード = TeamsOnly。|
|アクション|列挙型|*なし*、アップグレードを通知します。|これは、冗長モードと NotifySfbUsers の組み合わせであるために、最終的には削除され、従来のパラメーターです。 |
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
|UpgradeToTeams|TeamsOnly|False|Upgrade|チームにユーザーをアップグレードして、チャット、通話、およびビジネスのための Skype で会議のスケジュール設定をしないようにするのには、このモードを使用します。|
|グローバル|レガシー|False|なし|モードは、島に、近い将来に更新されます。|
|NoUpgrade|レガシー|False|なし|このインスタンスを破棄することが最終的には。|
|NotifyForTeams|レガシー|True|通知|このインスタンスを破棄することが最終的には。|
||||||

個々 のユーザーに、または、テナント全体では、これらのポリシーのインスタンスを与えることができます。 例:
- チームには、ユーザー ($SipAddress) をアップグレードするには、"UpgradeToTeams"のインスタンスを与えます。</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 全体のテナントをアップグレードするには、grant コマンドの id パラメーターを省略します。</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`



## <a name="teamsinteroppolicy-being-retired"></a>TeamsInteropPolicy が廃止されています。 

前述のように、TeamsUpgradePolicy、TeamsInteropPolicy は交換済み。 以前に TeamsInteropPolicy を適用するすべてのコンポーネントは、代わりに TeamsUpgradePolicy を有効に更新されています。 

マイクロソフトは、以前 TeamsInteropPolicy から TeamsUpgradePolicy でレガシー ・ モードへの移行を容易にするために「レガシ」モードを導入しました、TeamsUpgradePolicy を理解するためのルーティング コンポーネントは、TeamsInteropPolicy に戻すことができます。 TeamsUpgradePolicy を完全にサポートのルーティングおよびレガシー ・ モードを使用する必要性は不要です。 レガシー ・ モードを使用しているお客様の他のモードのいずれかを使用するのには TeamsUpgradePolicy の構成を更新する必要があります。 

レガシー ・ モードを使用してお客様は、TeamsInteropPolicy は以下の 3 つの特定インスタンスのみがサポートされていることが通知されます。 どちらの場合も、CallingDefaultClient の値には、ChatDefaultClient の値が一致して AllowEndUserClientOverride は常に false です。 
</br>
</br>
**TeamsUpgradePolicy モードを使用する場合は、TeamsInteropPolicy のインスタンスをサポートされているレガシの =**
|ID |AllowEndUserClientOverride|CallingDefaultClient|ChatDefaultClient|
|---|---|---|---|
|`DisallowOverrideCallingDefaultChatDefault`|False|既定|既定|
|`DisallowOverrideCallingSfbChatSfb`|False|デバイス|デバイス|
|`DisallowOverrideCallingTeamsChatTeams`|False|Teams|Teams|
|||||

$Policy が上記の id の値のいずれか、次のコマンドレットの構文を使用します。`Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

## <a name="federation-considerations"></a>フェデレーションに関する考慮事項

チームからビジネス用の Skype を使用して別のユーザーのフェデレーションでは、ビジネスの Skype でオンライン チームのユーザーが所属する必要があります。 最終的のビジネス、オンプレミス ユーザーが Skype で所属チームは他のチームのユーザーとフェデレーションを行うことになります。

TeamsUpgradePolicy は、受信フェデレーション チャットと通話のルーティングを制御します。 ユーザーが組織内でフェデレーション通信を開始する他の組織を容易にするをお勧めするいずれかの方法を具体的にはルーティング モードを選択する島ではなく、ビジネスまたはチームは、Skype にします。
</br>
|ルートの呼び出しとチャットをしています.|TeamsUpgradePolicy のインスタンスを許可します。</br> これらのモードのいずれかで
|---|---|
|Skype for Business|SfBOnly、SfBWithTeamsCollab、 </br>SfBWithTeamsCollabAndMeetings|
|Teams|TeamsOnly |
|||

受信者は、島のモードでは、チャットし、デバイスで着陸をフェデレーション ユーザーからの呼び出し。

## <a name="completing-the-transition-to-mode-management"></a>モードの管理への移行を完了します。

今年の後半、マイクロソフトは、新しいポリシーの種類、TeamsAppPermissionsPolicy、IM、会議、チャット チャンネル) などのチームのクライアントには、どの部分が有効になっているかを制御するために導入する予定です。 チームでの作業負荷を有効または無効にする新しいポリシーが利用可能になったら、TeamsUpgradePolicy が更新され、TeamsAppPolicy が適切であることを確認するのにはチェックが最初に管理者が TeamsUpgradePolicy のインスタンスをユーザーに許可しようとすると、ご希望のモードを構成します。 それ以外の場合は、補助金は、他のポリシーする必要があります最初の設定方法を説明するエラーで失敗します。 

TeamsAppPolicy が使用可能になるまで基本的には TeamsUpgradePolicy が呼び出しとチャットなどと同様の会議のスケジュール設定 (Outlook アドインで公開されている) とルーティングを制御します。 チームのクライアントの動作ではないためまだ場所には、現代のポータルのすべてのモードが有効になります。 ルーティングの観点から、SfBOnly、SfBWithTeamsCollab、および SfBWithTeamsCollabAndMeetings モードと同じです。 

## <a name="action-required-for-organizations-that-have-already-used-teamsinteroppolicy"></a>既に TeamsInteropPolicy を使用する組織に必要なアクション

レガシー ・ モードを使用しているユーザーは必要があります、次の操作を行います。

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

## <a name="detailed-mode-descriptions"></a>詳細モードの説明
</br>
</br>

|モード|解説|
|---|---|
|**諸島**|1 人のユーザーは、ビジネスとチーム サイド バイ サイドの両方の Skype を実行します。 次のユーザー:</br><ul><li>チャットを始めることができ、VOIP が企業やチームのクライアントのいずれかの Skype の呼び出しです。 注: ビジネス用の Skype でのユーザーのホーム サーバー別の Skype のビジネス ユーザーに到達するチームから設置を開始できません。<li>チャットとビジネス クライアント用の Skype の他のユーザーで Skype のビジネスを開始する VOIP 通話を受信します。<li>VOIP を受け取り、チームのクライアントで別のユーザーがチームで開始された呼び出しします。<li>チーム内で別のユーザーによるチャットが表示されます。<ul><li>ビジネス用の Skype には、受信者のホーム サーバーをオンラインとチームにログインしたことはありませんが用意されています。<li>他のすべてのケースでのチームです。</ul><li>次のように、PSTN の機能があります。<ul><li>設置型のビジネスで Skype ユーザーのホーム、PSTN の呼び出しが開始され、ビジネスの Skype で受信します。<li>ユーザーは、オンライン ホームでは、ユーザーが持っている電話システム ユーザーの場合。<ul><li>開始し、直接ルーティングするため、ユーザーが構成されている場合、チームで PSTN 通話を受信<li>開始し、ビジネス用の Skype で PSTN 通話を受信の場合、ユーザー、MS を呼び出すことを計画またはビジネス サーバー (ハイブリッド音声) のビジネス クラウド コネクタのエディションまたは Skype の設置型展開のいずれかの Skype 経由で PSTN ネットワークへの接続</ul></ul><li>チームやビジネス用の Skype で会議をスケジュールすることができます (と、既定では両方のプラグインを参照してください)。<li>任意の Skype ビジネスまたはチームの会議に参加できます。会議は、それぞれのクライアントに表示されます。</ul>|
|**SfBOnly**|1 人のユーザーには、ビジネスの Skype のみが実行されます。 次のユーザー:</br><ul><li>チャットおよびビジネス用の Skype からの呼び出しだけを実行できます。<li>コールを受信、チャット/ビジネスのクライアントに、Skype でに関係なく、開始、イニシエーターがビジネスのための Skype でのチームのユーザーでない限り、設置型のホームです。*<li>のビジネス会議、Skype のみをスケジュールすることができますが、Skype をビジネスまたはチームの会議に参加できます。</br> *、オンプレミスのユーザーとを使用する諸島モードが SfBOnly モードでは、他のユーザーとの組み合わせでお勧めしません。 設置型の呼び出し、または SfBOnly のユーザーとチャットを開始する場合は、ビジネスの Skype でのチームのユーザーのホーム、SfBOnly ユーザーが到達可能ではありませんし、失敗した呼び出しの email.* を受け取る|
|**SfBWithTeamsCollab**|1 人のユーザーは、ビジネスとチーム サイド バイ サイドの両方の Skype を実行します。 次のユーザー:</br><ul><li>SfBOnly モードでユーザーの機能を持ちます。<li>グループ作業 (チャネル) に対してのみ有効にチームチャット、通話、または会議のスケジュールが無効になります。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**</br>(予定)|1 人のユーザーは、ビジネスとチーム サイド バイ サイドの両方の Skype を実行します。 次のユーザー:<ul><li>SfBOnly モードでは、チャットとユーザーの呼び出し元の機能を持ちます。<li>チーム グループ コラボレーション対応 (チャネル)。チャットと通話を無効になります。<li>のみのチームのミーティングをスケジュールすることができますが、Skype をビジネスまたはチームの会議に参加できます。</ul>|
|**TeamsOnly**</br>(必要なデバイスのオンライン ホーム)|1 人のユーザーには、チームだけが実行されます。 次のユーザー:<ul><li>すべてのチャットを受信し、開始位置に関係なく、チームのクライアントで呼び出します。<li>チャットおよびチームからの呼び出しだけを実行できます。<li>のみ、チームでミーティングをスケジュールすることができますが、Skype をビジネスまたはチームの会議に参加できます。<li>ビジネス IP 電話の Skype を使用する続行できます。</ul> |
|**レガシー**</br>(既定値)|このモードは、ソフトウェアと一貫性のあるエクスペリエンスを TeamsInteropPolicy TeamsUpgradePolicy への移行中に使用された変更内容を公開します。このモードは、不要になった TeamsUpgradePolicy が完全にサポートされているようになりました。 モードを使用して顧客 = レガシが別のモードで使用するには、その構成を更新する必要があります。|
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
