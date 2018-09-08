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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1028f599b3b5cacf23fa920b85c42cf8a5bd4673
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884236"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>ビジネスのチームとは、Skype を使用する組織の移行と相互運用性のガイド

2018 年 4 月では、マイクロソフトからの移行チームに Skype ビジネスとどのようにこれら 2 つのクライアントが共存可能特定のユーザーのためのガイダンスを明示しました。 その時点では、管理の合理化し、エンド ・ ユーザーの満足度の向上に計画的な変更を発表しました。 以来、マイクロソフトは、その計画の一貫性のある管理者のユーザー エクスペリエンスでは、更新プログラムを配信しました。 このドキュメントでは説明には、それらの変更が反映されます。

以前に発表された (第 3 四半期の最後のターゲット)、TeamsInteropPolicy から退職して TeamsUpgradePolicy にその機能が統合されています。 相互運用と移行は、「共存モード」を使用して、現在利用可能な TeamsUpgradePolicy、によって管理されます。 ユーザーのモードの選択では、着信呼び出しとチャットの両方のルーティングとユーザーのチャットや通話を開始したり、会議をスケジュールするどのクライアントにします。 TeamsInteropPolicy から退職するときにも、phaseout の中に TeamsUpgradePolicy と同時に設定する必要があります。  

この取り組みの一環として、マイクロソフトでは「マイクロソフト チームと Skype のビジネス管理センター」(現代のポータルとも呼ばれます) 共存モードに基づいて、新しい管理モデルを反映するように最近更新しました。 現代のポータルを構成する TeamsUpgradePolicy はこれで自動的に設定も TeamsInteropPolicy に一貫性のある値は、TeamsInteropPolicy が不要になったユーザー インターフェイスで公開されているようです。 *ただし、PowerShell を使用して管理者が TeamsUpgradePolicy および TeamsInteropPolicy に適切なルーティングを確保する設定も必要があります。* TeamsUpgradePolicy への移行が完了した後、不要になった必要がありますも TeamsInteropPolicy を設定します。
</br>
</br>
|**相互運用と移行を管理します。**|**現代のポータル**|**PowerShell**|
|----|----|----|----|
|2018年 9 月 (変更される場合の日付) まで|TeamsUpgradePolicy を使用します。|TeamsUpgradePolicy と TeamsInteropPolicy の両方を使用します。 |
|2018年 9 月 (日付変更) を転記します。|TeamsUpgradePolicy を使用します。|TeamsUpgradePolicy を使用して、だけです。廃止 TeamsInteropPolicy|
|||||

共存モードの導入と TeamsInteropPolicy の保留中の退職後に、マイクロソフトは提供してこのガイドを今すぐチームを現在使用しているお客様は、移行を管理できるようにします。

## <a name="in-this-article"></a>この資料に記載されて

- [基本的な概念](#fundamental-concepts)
- [共存モード](#coexistence-modes)
- [TeamsUpgradePolicy: 移行と共存の管理](#teamsupgradepolicy-managing-migration-and-co-existence)
- [不要になった TeamsInteropPolicy](#teamsinteroppolicy-to-be-retired)
- [モードの管理への移行を完了します。](#completing-the-transition-to-mode-management)
- [既に TeamsInteropPolicy を使用する組織に必要なアクション](#action-required-for-organizations-that-have-already-used-teamsinteroppolicy)   
- [詳細モードの説明](#detailed-mode-descriptions) 
- [共存と移行を簡素化する計画的な機能変更の概要](#summary-of-planned-functionality-changes-to-simplify-coexistence-and-migration) 
- [既知の問題](#known-issues)

## <a name="fundamental-concepts"></a>基本的な概念

1.  *相互運用機能*: ビジネス ・ ユーザーの Lync と Skype とチームのユーザーの間で 1 対 1 の通信です。

2.  *フェデレーション*: ユーザーが別のテナントの間の通信します。

3.  すべてのビジネス アカウントを「ホーム」いずれかのオンラインのユーザーが、基になる Skype をあるチームまたは設置。
    - 既に Skype を使用してオンライン ビジネスのユーザーは、既存のオンライン アカウントを使用します。
    - 既に Skype を使用する設置型のビジネスと Lync ユーザーは、既存のオンプレミス アカウントを使用します。
    - ユーザーが対象となる、既存の Skype のビジネス アカウントを検出できませんが、Skype のオンライン ビジネスのアカウント チームのユーザーが作成されるときに自動的に準備があります。 Skype ビジネス ライセンスが必要ではありません。

4.  ビジネスまたは Lync では、いずれかの Skype の設置型展開があるし、それらのユーザーのチームのユーザーに、最低限、必ず Azure AD 接続が msRTCSIP-DeploymentLocator を同期しているビジネスのチームと Skype は、そのために AAD、属性オンライン、オンプレミス環境を正しく検出します。 さらに、チーム専用のモードを任意のユーザーを移動する (つまり、アップグレード、ユーザー)、 *Skype のビジネスのハイブリッド モードを構成する必要があります*。

5.  ビジネス ユーザーのチームと Skype との間の相互運用機能は、使用可能な*ビジネス用の Skype でチームのユーザーは、オンライン ホーム サーバーの場合*だけです。 Skype ビジネス ユーザーが所属することができますか、オンプレミス (と Skype をビジネスのハイブリッドの設定が必要です) またはオンラインです。 設置型のビジネスが Skype に置かれているユーザーは、(このドキュメントの後半で定義)、島のモードでチームを使用することができますが、チームを使用して、相互運用機能またはビジネスの Skype を使用して他のユーザーとフェデレーションを行うことはできません。  

6.  チームにユーザーをアップグレードするのには (モードでは TeamsUpgradePolicy を付与、つまり = TeamsOnly)、ビジネスの Skype のオンライン ユーザーのホーム必要があります。 これは、相互運用性、フェデレーション、およびチームのユーザーの完全な管理を確実に必要です。 ホーム設置型であるユーザーをアップグレードするのにを使用して、 `Move-CsUser` 、設置から管理用ツールの最初の移動に Skype ユーザーは、オンライン ビジネスです。 次 TeamsUpgradePolicy と TeamsInteropPolicy をオンラインのユーザーに付与または TeamsOnly モードを割り当てるには、現代のポータルを使用します。

7.  アップグレードと相互運用機能を管理するための中核となるポリシーは、TeamsUpgradePolicy と TeamsInteropPolicy です。  ただし、TeamsInteropPolicy が廃止されている、すべての機能の方は TeamsUpgradePolicy が優先されます。 移行が完了するまで、顧客が設定 TeamsUpgradePolicy と TeamsInteropPolicy の両方一貫して (説明した[後](#important)でこのドキュメント) を正しく機能させる、または自動的には、この新しい近代的なポータルを使用して必要があります。

8.  チームの電話システムの機能を使用するユーザー必要がありますモードでは TeamsOnly (すなわち、Skype でオンライン ビジネスのホームをアップグレードしてチーム)、および Microsoft 電話システム直接ルーティングする (これは、独自の SIP の電話システムを使用できるように構成する必要がありますかトランクと SBC) ことも、Office 365 を呼び出すことを計画します。 直接ルーティングは、[一般に利用可能な](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277)2018 年 6 月 28 日の時点で。  

9.  オーディオ会議でチームのミーティングのスケジュール (ダイヤルインまたはダイヤルアウトを PSTN 経由で) は、オンライン ビジネスの Skype をホームとしているユーザーにのみ現在利用可能です。 オンプレミス Skype のビジネス アカウントでチームのユーザーのサポートを計画します。

10. 組織ではないまだ有効になっている統合プレゼンス サービス (UPS) のメッセージのルーティングは使用できない TeamsInteropPolicy (ChatDefaultClient) または TeamsUpgradePolicy (モード) のいずれかです。 UPS の導入は、今後数週間以内に完了すると、TeamsInteropPolicy または TeamsUpgradePolicy が受け入れられます。 最終的に唯一の TeamsUpgradePolicy は受け入れられます。

## <a name="coexistence-modes"></a>共存モード

管理の合理化とエンド ・ ユーザーの満足度を高め、相互運用と移行管理されていますが TeamsUpgradePolicy を使用して「共存モード」にします。 ユーザーのモードを決定します。

- *着信ルーティング*: クライアント (チームやビジネス用の Skype) は、どの着信チャットで着陸を呼び出しますか? この機能には、何が、TeamsInteropPolicy が処理していたが置き換えられます。 TeamsInteropPolicy は、移行が完了した後に退職します。 ***、移行中に TeamsUpgradePolicy と TeamsInteropPolicy の両方設定されている、組織的な方法で、次のセクションで説明***します。
- *会議のスケジュール設定*: 新しい会議をスケジュールしたり、適切なアドインが存在する Outlook でどのサービスを使用しますか? Outlook アドインのサポートは、今後数週間で展開する必要があります。 TeamsUpgradePolicy では、会議の参加は制御されませんに注意してください。 ユーザーが常に*結合*すべての会議では、ビジネス会議やチーム会議、Skype であるかどうか。
- *クライアントで発生する*: どのような機能は、ビジネス クライアントのチームや Skype で利用できるでしょうか。 これは TeamsOnly モードを実装します。 他のモードのサポートは、今後の TeamsAppPolicy に依存します。 この新しいポリシーが適用されて、TeamsUpgradePolicy はチームが必要なモードを正しく構成されていることを確認することで、依存関係にがあります。

計画モードは次のとおりです。 SfBWithTeamsCollab と SfBWithTeamsCollabAndMeetings は、重複機能を持つが、両方のクライアントの混在の使用をことができません。 アイランド モードでは、機能が重複しているのですが、両方のクライアントの使用の状況を許可します。 たとえば、諸島モードでは、ユーザーはビジネスやチームのいずれかの Skype でチャットを開始する可能性がありますが、SfBWithTeamsCollab、ビジネスの Skype のことができますチャットのみです。 ないモードがまだ使用できることに注意してください。  
</br>
</br>
|モード|ルーティング動作|会議のスケジュール|クライアント エクスペリエンス|
|---|---|---|---|
|諸島|着信 VOIP を呼び出し、開始者<sup>1</sup>と同じクライアントでの着陸のチャット|両方|エンド ・ ユーザーは、呼び出しと、クライアントでは、チャットを開始できるし、クライアントの会議をスケジュールすることができます。|
|SfBOnly|着信呼び出しとのチャットは、Skype のビジネスにルーティングされます。|Skype ビジネスだけに|エンド ・ ユーザーでは、呼び出しとのみ、ビジネスの Skype のチャットを開始でき、のみ Skype のビジネス ・ ミーティングのスケジュールを設定することができます。 (適用されていません)|
|SfBWithTeamsCollab<sup>2</sup>|着信呼び出しとのチャットは、Skype のビジネスにルーティングされます。|Skype ビジネスだけに|エンド ・ ユーザーでは、呼び出しとのみ、ビジネスの Skype のチャットを開始でき、のみ Skype のビジネス ・ ミーティングのスケジュールを設定することができます。 チームでチャネルを使用することもできます。 (適用されていません)|
|SfBWithTeamsCollabAndMeetings<sup>3</sup>|着信呼び出しとのチャットは、Skype のビジネスにルーティングされます。|チームのみ|エンド ・ ユーザーが呼び出しを開始し、ビジネスしかし、唯一の Skype からチャットは、チームのミーティングをスケジュールします。 チームでチャネルを使用することもできます。 (適用されていません)|
|TeamsOnly|着信呼び出しとのチャットは、チームに送られます|チームのみ|エンド ・ ユーザーには、呼び出しとチームからのチャットのみを開始できます。 ビジネス用の Skype には、ミーティングに参加するのにはできるだけです。|
|レガシー|TeamsInteropPolicy に基づくルーティング|影響なし|影響はありません。 この TeamsInteropPolicy から TeamsUpgradePolicy への移行を容易にするために一時的なモードです。 移行が完了した後は、このモードが削除されます。 |
|||||

**メモ:**

<sup>1</sup> PSTN の呼び出しの詳細については、このドキュメントの最後にある表を参照してください。

<sup>2</sup> SfBWithTeamsCollab はまだ公開されません管理者のユーザー エクスペリエンスのため、現在の動作モードの SfBOnly を区別なく。 クライアント エクスペリエンスが配信されると、このモードが表示されます。

<sup>3</sup> SfBWithTeamsCollabAndMeetings はまだ使用できません。 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: 移行と共存の管理

TeamsUpgradePolicy は、ここで 3 つのプロパティを公開します。 主プロパティは、モードと NotifySfbUsers です。 アクション従来のパラメーターは、モードと NotifySfbUsers の組み合わせを完全に冗長化されました。
</br>
</br>
|パラメーター|種類|許容値</br>(イタリック体での既定値)|説明|
|---|---|---|---|
|モード|列挙型|*諸島*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>レガシー|クライアントを実行する必要がありますモードを示します。 場合モード = レガシでは、このポリシーを使用するコンポーネントは、TeamsInteropPolicy に従うことに戻されます。 これは、以前 TeamsInteropPolicy を適用するコンポーネントの TeamsUpgradePolicy を優先する更新は新しいスキーマへの移行を支援します。</br>モード = TeamsOnly は、アクションのアップグレードを = します。|
|NotifySfbUsers|ブール値|*False*または true|チームはビジネス用の Skype を交換してすぐにユーザーに通知するビジネス クライアント用の Skype のバナーを表示するかどうかを示します。 これは true を指定することはできない場合モード = TeamsOnly。 アクションと同じではこの通知を = します。|
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
|グローバル|レガシー|False|なし|モードは、最終的に島に更新されます。|
|NoUpgrade|レガシー|False|なし|このインスタンスを破棄することが最終的には。|
|NotifyForTeams|レガシー|True|通知|このインスタンスを破棄することが最終的には。|
||||||

個々 のユーザーに、または、テナント全体では、これらのポリシーのインスタンスを与えることができます。 例:
- チームには、ユーザー ($SipAddress) をアップグレードするには、"UpgradeToTeams"のインスタンスを与えます。</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 全体のテナントをアップグレードするには、grant コマンドの id パラメーターを省略します。</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

### <a name="important"></a>大事な！
以前に TeamsInteropPolicy を適用するコンポーネントは、TeamsUpgradePolicy を優先する更新を進めています。 、移行中にこれら 2 つのポリシーの管理は、以下に示す調整する必要があります。 現代のポータルへの新しい更新プログラムが自動的に付与これらのポリシーの両方の正しく共存モードを選択するときに注意してください。
</br>
</br>
|TeamsUpgradePolicy のインスタンスを許可する場合</br>このモード値を持つ.|.TeamsInteropPolicy のこのインスタンスを許可し、|
|---|---|
|諸島|`DisallowOverrideCallingDefaultChatDefault`|
|SfBOnly、SfBWithTeamsCollab、</br>SfBWithTeamsCollabAndMeetings|`DisallowOverrideCallingSfbChatSfb`|
|TeamsOnly |`DisallowOverrideCallingTeamsChatTeams`|
|||

## <a name="teamsinteroppolicy-to-be-retired"></a>不要になった TeamsInteropPolicy 

前述のように、TeamsInteropPolicy は TeamsUpgradePolicy によって置き換えられます。 この移行が完了するまで、TeamsInteropPolicy は以下の 3 つの特定インスタンスのみがサポートされます。 どちらの場合も、CallingDefaultClient の値には、ChatDefaultClient の値が一致して AllowEndUserClientOverride は常に false です。 
</br>
</br>
**退職する前に、TeamsInteropPolicy のサポートされているインスタンス**
|ID |AllowEndUserClientOverride|CallingDefaultClient|ChatDefaultClient|
|---|---|---|---|
|`DisallowOverrideCallingDefaultChatDefault`|False|既定|既定|
|`DisallowOverrideCallingSfbChatSfb`|False|デバイス|デバイス|
|`DisallowOverrideCallingTeamsChatTeams`|False|Teams|Teams|
|||||

$Policy が上記の id の値のいずれか、次のコマンドレットの構文を使用します。`Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

## <a name="federation-considerations"></a>フェデレーションに関する考慮事項

チームからビジネス用の Skype を使用して別のユーザーのフェデレーションでは、ビジネスの Skype でオンライン チームのユーザーが所属する必要があります。 フェデレーションでは、パイロットと段階的に利用可能になります。 組織では、フェデレーションが必要とする場合は、フェデレーションのサポートになるまではアップグレードしないでください。 最終的のビジネス、オンプレミス ユーザーが Skype で所属チームは他のチームのユーザーとフェデレーションを行うことになります。

フェデレーション サポートを有効にすると、TeamsUpgradePolicy (および移行中に TeamsInteropPolicy) は、受信フェデレーション チャットと通話のルーティングを制御します。 ユーザーが組織内でフェデレーション通信を開始する他の組織を容易にするをお勧めするいずれかの方法を具体的にはルーティング モードを選択する島ではなく、ビジネスまたはチームは、Skype にします。
</br>
|ルートの呼び出しとチャットをしています.|TeamsUpgradePolicy のインスタンスを許可します。</br> これらのモードのいずれかで|TeamsInteropPolicy のこのインスタンスを与えると|
|---|---|---|
|Skype for Business|SfBOnly、SfBWithTeamsCollab、 </br>SfBWithTeamsCollabAndMeetings|`DisallowOverrideCallingSfbChatSfb`|
|Teams|TeamsOnly |`DisallowOverrideCallingTeamsChatTeams`|
||||

## <a name="completing-the-transition-to-mode-management"></a>モードの管理への移行を完了します。

今年の後半、マイクロソフトは、新しいポリシーの種類、TeamsAppPolicy、IM、会議、チャット チャンネル) などのチームのクライアントには、どの部分が有効になっているかを制御するために導入する予定です。 チームでの作業負荷を有効または無効にする新しいポリシーが利用可能になったら、TeamsUpgradePolicy が更新され、TeamsAppPolicy が適切であることを確認するのにはチェックが最初に管理者が TeamsUpgradePolicy のインスタンスをユーザーに許可しようとすると、ご希望のモードを構成します。 それ以外の場合は、補助金は、他のポリシーする必要があります最初の設定方法を説明するエラーで失敗します。 

TeamsAppPolicy が使用可能になるまで基本的には TeamsUpgradePolicy が呼び出しとチャットなどと同様の会議のスケジュール設定 (Outlook アドインで公開されている) とルーティングを制御します。 チームのクライアントの動作ではないためまだ場所には、現代のポータルのすべてのモードが有効になります。 ルーティングの観点から、SfBOnly、SfBWithTeamsCollab、および SfBWithTeamsCollabAndMeetings モードと同じです。 

## <a name="action-required-for-organizations-that-have-already-used-teamsinteroppolicy"></a>既に TeamsInteropPolicy を使用する組織に必要なアクション

これらの今後の変更の準備として、お客様は、次の。

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
|**レガシー**</br>(既定値)|TeamsInteropPolicy アウト フェーズは、移行中にこのモードが使用されます。 さまざまな時点で TeamsUpgradePolicy を使用するシステムのさまざまなコンポーネントが更新されます。 、この移行中にこのモードを持つユーザーは引き続き既存の TeamsInteropPolicy 値を優先します。 これにより、サービスのさまざまなコンポーネントがさまざまな時点で更新される場合でも、一貫性のあるユーザー エクスペリエンスです。|
|||

## <a name="summary-of-planned-functionality-changes-to-simplify-coexistence-and-migration"></a>共存と移行を簡素化する計画的な機能変更の概要

マイクロソフトは、タップの顧客およびその他の初期採用者からの強力なフィードバックに基づき、管理を簡素化し、チームにビジネス用の Skype から移行する組織では、エンド ・ ユーザーの満足度を高めるには、年 4 月に予定されている変更を発表しました。 これらの変更は、アップグレードと相互運用性を管理するためのポリシーの簡略化されたモデルを使用して、簡略化し、予測可能なエンド ・ ユーザーのエクスペリエンスを提供します。 次の変更は、次の数か月間段階的ロールアウトは。 高レベルでは、次に示す、4 つの計画的な機能変更があります。
</br>
</br>
**変更 1: これ以上重複している様相優先するクライアントが設定されている場合**
|||
|---|---|
|**意思決定**|*ユーザーの優先するクライアントは、「チーム」または「デバイス」のいずれかに設定されている場合*特定のモード (IM 会議のスケジュール設定、呼び出し) のみが利用できるようユーザーの 1 つのクライアント (チームやビジネス用の Skype) でサポートされています。 (*優先クライアント*は、TeamsInteropPolicy の DefaultChatClient および DefaultCallingClient パラメーターを参照)。推奨されるクライアントが (将来「孤立モード」と呼ばれます) では、"Default"に設定されている場合にのみ指定されたモードが利用できるよう両方のクライアントでサポートされています。 |
|**理論的根拠**|様相を重ねて両方のクライアントを使用しようとするとき、理由の 1 つまたは別のユーザーが混乱し、一貫性のある私達が受け取ったフィードバックです。 予測し、メッセージと呼び出しが 1 つのクライアントと、別の着陸し、プレゼンスは、不正確または誤解を招く理由を理解するのには困難です。|
|**状態**|モードのサポートは、この TeamsOnly を = します。 他のモードのサポートは今後数か月で利用可能になります。 |
|||

**変更 2: メッセージと呼び出しの優先するクライアントを統合します。**
|||
|---|---|
|**意思決定**|マイクロソフトは IM と呼び出しの優先するクライアントの管理を統一します。 具体的には、DefaultChatClient と DefaultCallingClient で同じ値のいずれか両方既定値 (諸島)、チーム、またはビジネスの両方の Skype の両方が必要です。  |
|**理論的根拠**|これらが一致しない場合は、プレゼンスもなります誤解や混乱を招く。 さらに、既存のチャットからの呼び出しを開始する可能性があります混乱の呼び出しは、既存のチャットよりも別のクライアントに着陸可能性。 |
|**状態**|この変更は、管理者のユーザー エクスペリエンス (最近ポータル) でだけでなく、TeamsUpgradePolicy を使用してポリシーの層で実装されています。 ただし、移行がまだ完了、お客様は、TeamsInteropPolicy にも設定する必要がありますようにです。 顧客でのみ設定される TeamsInteropPolicy の 3 つサポートされているインスタンスのいずれかする必要があります: DisallowOverrideCallingTeamsChatTeams、DisallowOverrideCallingDefaultChatDefault、DisallowOverrideCallingSfbChatSfb|
|||

**変更 3: 複数エンド ・ ユーザーを選択しない優先するクライアントの**
|||
|---|---|
|**意思決定**|エンド ・ ユーザーは、優先するクライアントを選択します。 (TeamsInteropPolicy の AllowEndUserClientOverride は false に設定する必要があります)。推奨されるクライアントは、に基づいてモードでは、管理者によって設定されますが、|
|**理論的根拠**|利用状況データの分析は、ユーザーはほとんどありませんがこの設定を示しています。 この選択を排除することでは、管理者またはヘルプデスクのシナリオを効率化し、エンジニア リングの複雑さを軽減します。 最後に、エンド ・ ユーザー、管理者がエンタープライズ VoIP を持つ組織での音声ルーティングの構成から別の推奨されるクライアントを選択する場合は、これが原因で、エンド ユーザー エクスペリエンスに混乱 VOIP になるため、PSTN の呼び出しが別の着陸クライアントです。|
|**状態**|この変更は、管理者のユーザー エクスペリエンス (最近ポータル) でだけでなく、TeamsUpgradePolicy を使用してポリシーの層で実装されています。 ただし、移行がまだないオーバーライドを禁止すべてのコマンドレットを使用しているお客様は TeamsInteropPolicy を TeamsInteropPolicy の 3 つのサポートされているインスタンスのいずれかに設定する必要がありますので、完了します。|
|||

**4: 管理に基づくクライアントの [モード]**
|||
|---|---|
|**意思決定**|チームを採用する組織のビジネスの Skype を使用すると、クライアントの動作を管理するには、「モード」概念が導入されていますいます。 管理者は、ユーザーごとのごとにモードを設定することができ、ユーザーのモードは、どのような機能は、クライアントで使用可能なドライブは通話とチャットが着陸とします。 管理者がこのモードをサポートするアップデートされた改訂版の TeamsUpgradePolicy を使用して管理されます。 TeamsInteropPolicy は、最終的には非推奨し、する TeamsUpgradePolicy からの読み取りにすべてのコンポーネントが更新された後、削除します。|
|**理論的根拠**|管理の合理化し、エンド ・ ユーザーの満足度を高め、相互運用と移行が管理する TeamsUpgradePolicy を使用して「共存モード」を使用します。 ユーザーのモードの選択では、チャット、および着信通話のルーティングとユーザーのチャットや通話を開始したり、会議をスケジュールするどのクライアントにします。 TeamsUpgradePolicy と TeamsInteropPolicy の統合は、またこれら 2 つのポリシーが一貫して設定されていない可能性があります構成の誤りを防止します。 |
|**状態**|タップのお客様は、今すぐ管理エクスペリエンスの 3 つのモードを参照してください。 変更 1 土地のサポート、その他のモードが利用できます。 SfBOnly モードは現在は禁止、チームを使用しますが、将来的にします。 |
|||

## <a name="known-issues"></a>既知の問題

- をチームで新しい会話を作成するときのチャットもまだ認めません TeamsUpgradePolicy または移動先のユーザーの TeamsInteropPolicy。 修正プログラムが予定されています。
- をビジネス用の Skype の新しい会話を作成するときのチャットもまだ認めません TeamsUpgradePolicy または TeamsInteropPolicy 組織は UPS とメッセージングの相互運用機能をまだ有効になっていない場合です。

## <a name="related-topics"></a>関連トピック

[Get CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsinteroppolicy?view=skype-ps)

[許可 CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsinteroppolicy?view=skype-ps)

[削除 CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsinteroppolicy?view=skype-ps)

[Get CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Get CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[許可 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[新しい-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsupgradepolicy?view=skype-ps)

[削除 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsupgradepolicy?view=skype-ps)

[セット CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[セット CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradepolicy?view=skype-ps)
