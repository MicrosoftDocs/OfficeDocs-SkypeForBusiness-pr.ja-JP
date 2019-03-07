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
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebefcf81eace90f99b2871fcd7232f799af3edb2
ms.sourcegitcommit: 2dd1369e5112b0c4ed7c6b0be8a17489b71f494a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30469771"
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
    - ユーザーが対象となる、既存の Skype のビジネス アカウントを検出できませんが、Skype のオンライン ビジネスのアカウント チームのユーザーが作成されるときに自動的に準備があります。

4.  ビジネスまたは Lync では、いずれかの Skype の設置型展開があるし、それらのユーザーのチームのユーザーに、最低限、必ず Azure AD 接続が msRTCSIP-DeploymentLocator を同期しているビジネスのチームと Skype は、そのために AAD、属性オンライン、オンプレミス環境を正しく検出します。 さらに、チーム専用のモードを任意のユーザーを移動する (つまり、アップグレード、ユーザー)、*ビジネスのハイブリッド モードの Skype を最初に構成する必要があります*。 詳細については、 [Skype のビジネスとチームの構成の Azure AD の接続](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect)を参照してください。

5.  ビジネス ユーザーのチームと Skype との間の相互運用機能は、使用可能な*ビジネス用の Skype でチームのユーザーは、オンライン ホーム サーバーの場合*だけです。 Skype ビジネス ユーザーが所属することができますか、オンプレミス (とビジネスのハイブリッドの Skype を設定する必要があります) の受信者またはオンラインです。 設置型のビジネスが Skype に置かれているユーザーは、(このドキュメントの後半で定義)、島のモードでチームを使用することができますが、チームを使用して、相互運用機能またはビジネスの Skype を使用して他のユーザーとフェデレーションを行うことはできません。  

6.  アップグレードと相互運用機能の動作は、下に後で説明されている、ユーザーの共存モードに基づいて決定されます。 モードは、TeamsUpgradePolicy によって管理されます。 TeamsInteropPolicy は、受取済および許可モードではありません = レガシーは許可されていません。 

7.  TeamsOnly モードにユーザーをアップグレードする、すべての着信のチャットや通話は常にどのようなクライアントに関係なく、ユーザーのチームのクライアントに着陸できるようにから orignated を保証します。 これらのユーザー、チーム内のすべての新しい会議をスケジュールしてもします。 TeamsOnly モードにするには、ユーザーする必要がありますが所属するオンライン ビジネスの Skype にします。 これは、相互運用性、フェデレーション、およびチームのユーザーの完全な管理を確実に必要です。ユーザーを TeamsOnly にアップグレードするには。
    - ユーザーのオンライン ホーム ビジネスのための Skype の場合 (または任意の Skype アカウントがなかった)、モードで TeamsUpgradePolicy を与えた = PowerShell を使用して"UpgradeToTeams"のインスタンスを使用して TeamsOnly または TeamsOnly モードを選択するチームの管理センターを使用します。
    - 使用して、ユーザーがホームの設置型の場合は、 `Move-CsUser` 、設置から管理用ツールの最初の移動に Skype ユーザーは、オンライン ビジネスです。  かどうかがある Skype ビジネス サーバー 2019 または CU8 の Skype のビジネス サーバー 2015 の指定すること、`-MoveToTeams`でスイッチを`Move-CsUser`、移動の一部としてチームに直接ユーザーを移動するのにはオンラインです。 (ただし、ここでは、会議の移行のみタップ向け機能) このオプションはチームにもユーザーの会議を移行します。 場合`-MoveToTeams`は利用できない、または指定された後、`Move-CsUser`が完了したら、PowerShell またはチームの管理センターを使用してそのユーザーに TeamsOnly モードを割り当てます。 詳細については、[オンプレミスとクラウドの間でユーザーの移動](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)を参照してください。  会議の移行の詳細については、「[会議の移行サービス (MMS)](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」を参照してください。

8.  チームとチームの電話システムの機能を使用するユーザーは TeamsOnly モード (すなわち、Skype でオンライン ビジネスのホームをアップグレードしてチーム) である必要があり、マイクロソフトの電話システムに[直接ルーティングの場合](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277)(これは電話システムを使用できるように構成する必要がありますか独自の SIP トランクおよび SBC を使用して) を持つことも、Office 365 を呼び出すことを計画します。   

9.  オーディオ会議でチームのミーティングのスケジュール (ダイヤルインまたはダイヤルアウトを PSTN 経由で) は、オンライン ビジネスの Skype をホームとしているユーザーにのみ現在利用可能です。 オンプレミス Skype のビジネス アカウントでチームのユーザーのサポートは、タップでは。


## <a name="coexistence-modes"></a>共存モード

相互運用と移行は、TeamsUpgradePolicy を使用して「共存モード」に基づいて管理されます。 共存モード エクスペリエンスを提供シンプルで予測可能なエンド ・ ユーザーの組織の移行とビジネス用の Skype からチームにします。 チームに移動する組織、TeamsOnly モードは、各ユーザーの最終的な宛先を同時に TeamsOnly (またはいずれかのモード) に割り当てられる必要はないすべてのユーザーです。 ユーザー モードの TeamsOnly に到達する前に組織に使用できます、Skype のビジネス ・ モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) は、TeamsOnly ユーザーは、まだない方の間で予測可能な通信を確保します。


、技術的な観点からは、ユーザーのモードは、ユーザーの経験のいくつかの側面を制御します。

- *着信ルーティング*: クライアント (チームやビジネス用の Skype) は、どの着信チャットで着陸を呼び出しますか? 
- *プレゼンスの発行*: チームやビジネス用の Skype では、ユーザーのアクティビティに基づいて他のユーザーに表示されているユーザーのプレゼンスは、ですか。 
- *会議のスケジュール設定*: 新しい会議をスケジュールしたり、適切なアドインが存在する Outlook でどのサービスを使用します。 TeamsUpgradePolicy では、会議の参加は制御されませんに注意してください。 ユーザーが常に*結合*すべての会議では、ビジネス会議やチーム会議、Skype であるかどうか。
- *クライアントで発生する*: どのような機能は、ビジネス クライアントのチームや Skype で利用できるでしょうか。 ユーザーに呼び出し、チーム、ビジネス用の Skype またはその両方でチャットを開始できますか。 あるチームの & のチャンネルが発生するでしょうか。  この資料の後半で説明したとおり、モードのこの最後の側面はここで配信される開始します。

モードに基づいて、ルーティングとプレゼンスの動作の詳細については、 [Skype のビジネスとの共存](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence)を参照してください。

ただし、経験の観点からモードよりシンプルの説明としての経験を定義します。
- *チャットし、呼び出し*: ユーザーに使用しているクライアントですか?
- *会議のスケジュール設定*: ユーザーのチームまたは Skype としてビジネス会議のための新しい会議をスケジュールしますか?
- *チームのクライアントでコラボレーション機能の可用性*です。 チームの & チャネルとファイルの機能は利用可能なユーザーでは、ビジネス用の Skype もありますが

モードは次のとおりです。
</br>
</br>

|モード|通話とチャット|会議スケジュール<sup>1</sup>|チームの & チャネル|大文字と小文字を使用します。|
|---|---|---|---|---|
|**TeamsOnly**</br>*ビジネス オンラインの Skype のホームが必要*|Teams|Teams|あり|アップグレード中の最終的な状態です。 _LT_500 シートの新しいテナントのデフォルトです。|
|アイランド|いずれも|いずれも|あり|既定の構成です。 両方のクライアント サイド バイ サイドを評価するために 1 人のユーザーを使用できます。 チャットや通話は、ユーザーは、両方のクライアントに常に実行する必要がありますのでいずれかのクライアントで着陸できます。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|あり|"会議最初"です。 されていない場合、チームの会議の機能を利用しながら、クラウドへの呼び出しモードの準備ができたの設置型の組織を主に|
|SfBWithTeamsCollab<sup>2</sup>|Skype for Business|Skype for Business|あり|管理制御の精度を必要とする複雑な組織の別の開始点|
|SfBOnly|Skype for Business|Skype for Business|なし<sup>3</sup>|シナリオは、データ コントロールの周囲の厳格な要件を持つ企業に特化しています。 チームは他のユーザーによってスケジュールされたミーティングへの参加にのみ使用されます。|
||||||

</br>
</br>

**メモ:**

<sup>1</sup> (またはビジネス用の Skype のチームで予定されている) かどうか、既存の会議に参加することは、モードによって制御されていません。 既定では、ユーザーは常に招待されているすべての会議を結合できます。

<sup>2</sup> SfBWithTeamsCollab と SfBWithTeamsCollabAndMeetings は、PowerShell では、現在利用可能なのみです。  完了したクライアント エクスペリエンスを提供すると後、これらのモードは管理ポータルで使用可能になります。 

<sup>3</sup>現在、チームは存在しないので、これは有効のままここでは、チームとチャネルの機能を無効にする機能です。



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

チームからビジネス用の Skype を使用して別のユーザーのフェデレーションでは、ビジネスの Skype でオンライン チームのユーザーが所属する必要があります。 最終的には、ビジネス、オンプレミス ユーザーが Skype で所属チームはチームのみのユーザーのフェデレーションを行うことになります。

TeamsUpgradePolicy は、受信フェデレーション チャットと通話のルーティングを制御します。 フェデレーション ルーティングの動作は、*諸島モードで*は、同じテナントのシナリオの場合と同じです。  受信者は、島のモードでは。 
- チャットおよびチームから開始された呼び出しは、受信者が*フェデレーションのテナント*の場合はデバイスに着陸します。
- チャットおよびチームから開始された呼び出しは、受信者が*同じテナント*内にある場合はチームで着陸します。
- チャットと常にデバイスから開始された呼び出しは、ビジネスの Skype で着陸します。

詳細については、 [Skype のビジネスとの共存](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence)を参照してください。

## <a name="the-intended-client-user-experience-in-teams-when-using-sfb-modes"></a>デバイスのモードを使用すると、チームで対象のクライアントのユーザーが発生します。
ユーザーは、Skype のビジネス ・ モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) のいずれかでは、ビジネスのクライアントのユーザーの Skype にすべての着信のチャットや通話がルーティングされます。 エンド ・ ユーザーの混乱を防止し、適切なルーティングを確保、チーム クライアントでの通話やチャット機能は、*ユーザーは、Skype のビジネス モードのいずれかで、無効にするためのもので*。 同様に、チームでミーティングのスケジュール設定*SfBOnly または SfBWithTeamsCollab のモードでは、ユーザーに明示的に無効にするためのもの*は、ユーザーが SfBWithTeamsCollabAndMeetings モードである場合を明示的に有効にします。 

### <a name="automatic-conformance-of-teams-client-based-on-mode-planned"></a>(計画) モードに基づくチームのクライアントの自動準拠 
チャットとモードに基づいて、有効/無効にする会議のスケジュールとともに、機能の呼び出しを自動的に無効にするための機能今すぐタップの顧客へのロールアウトを開始するが、まだ広く利用可能ではありません。 新機能の詳細については、[クライアント エクスペリエンスのチームとの共存モードへの準拠](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)を参照してください。

### <a name="manual-configuration-of-workload-policy-settings-prior-to-automatic-conformance"></a>自動一致する前に、ワークロード ポリシーの設定を手動で構成
このソリューションまでモードへの自動準拠は、配信の管理者を強制できます TeamsUpgradePolicy モードの対象のクライアント エクスペリエンスの TeamsMessagingPolicy、TeamsCallingPolicy、値を手動で構成し、TeamsMeetingPolicy。 使用すると、さらに、`Grant-CsTeamsUpgradePolicy`これらの設定は指定したモードと互換性がある場合では PowerShell では、コマンドレットが determmine TeamsMessagingPolicy、TeamsCallingPolicy、および TeamsMeetingPolicy の対応する設定の構成を確認します。 いずれかが正しく構成されていません場合、は、補助金は成功しますが、どの設定が正しく構成されていないことを示す警告が提供されます。 管理者は、チームで互換性のあるエンド ユーザー エクスペリエンスを提供するのには示されているポリシーを更新する必要があります後。 管理者は、警告の結果としてのアクションは実行しませんが場合、ユーザー可能性があります、チャットへのアクセスを呼び出すと、または会議の TeamsMessagingPolicy、TeamsCallingPolicy、TeamsMeetingPolicy の値に応じてチームでのスケジュール設定機能エンド ユーザー エクスペリエンスに混乱する可能性があります。

TeamsUpgadePolicy が付与されるとするポリシーの設定がチェック アウトの詳細は、[クライアント エクスペリエンスのチームとの共存モードへの準拠](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)を参照してください。


**注:** 開始前に上記で説明したクライアントの動作の自動強制、デバイス モードの各動作が基本的に同じです。 SfBOnly、SfBWithTeamsCollab、および SfBWithTeamsCollabAndMeetings モードでは、チャットおよび着信呼び出しのルーティングにすべて同じです。 唯一の違いは、チームの Outlook アドインとビジネス用の Skype が有効になっているかどうかにします。 差別化されたクライアントのクライアントが配信されるまでは、管理ポータルで、デバイスのモードの 1 つだけが有効になります。 すべてのモードでは、PowerShell で使用できます。


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

[Teams のクライアント エクスペリエンスおよび共存モードへの準拠](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[許可 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[セット CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)


