---
title: 移行と相互運用性 - Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 組織の移行を管理するための基本的な概念を理解Teams移行Skype for Business。
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
ms.openlocfilehash: 96aeda2b14d2aa3dedd810317865f3d02e29f68a
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305954"
---
# <a name="coexistence-modes---reference"></a>共存モード - リファレンス

共存モードは、組織が組織を新しい環境に移行する中で、エンド ユーザーに単純で予測可能Skype for Business提供Teams。 Teams に移行する組織にとって、各ユーザーの最終的な目的地は TeamsOnly モードですが、すべてのユーザーに TeamsOnly (またはその他のモード) を同時に割り当てる必要はありません。 TeamsOnly モードに到達する前に、組織は任意の Skype for Business モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) を使用して、TeamsOnly であるユーザーとまだないユーザーの間で予測可能な通信を確保できます。

技術的な観点から、ユーザーのモードは、ユーザーのエクスペリエンスのいくつかの側面を制御します。

- *受信ルーティング*: 受信チャットと通話が、どのクライアント (Teams または Skype for Business) に届くのか。 
- *プレゼンス公開*: 他のユーザーに表示されるユーザーのプレゼンスが、Teams または Skype for Business のいずれのアクティビティに基づいたものなのか。 
- *会議のスケジュール*: 新しい会議のスケジュール、そして適切なアドインが Outlook に存在することを確認するのに使用されるサービスはどれなのか。 TeamsUpgradePolicy では、会議への参加は管理されない。 ユーザーは常に、Skype for Business または Teams のいずれの会議であっても、*参加* することができます。
- *クライアント エクスペリエンス*: Teams または Skype for Business で利用可能な機能はどれなのか。 ユーザーは通話やチャットをTeams、Skype for Business、または両方で開始できますか。 チームとチャンネルのエクスペリエンスは使用可能なのか。  

モードに基づくルーティングとプレゼンスの動作の詳細については、「アプリケーションとの共存[」をSkype for Business。](./coexistence-chat-calls-presence.md)

ただし、エクスペリエンスの観点から、モードは次のエクスペリエンスを定義するとして記述できます。
- *チャットと通話*: ユーザーが使用するクライアントはどれなのか。
- *会議のスケジュール*: ユーザーは新しい会議を Teams と Skype for Business のいずれの会議としてスケジュールするのか。
- *Teams クライアントでの共同作業機能の使用可能性*。 ユーザーがまだ Skype for Business を所有している場合、チームとチャンネル、およびファイル機能を使用できるかどうか。

モードの一覧を次に示します。
</br>
</br>

|モード|通話とチャット|会議のスケジュール<sup>1</sup>|チームとチャンネル|使用例|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*ユーザーがオンプレミスアカウントを持ってない場合にのみSkype for Business Server*|Teams|Teams|あり|アップグレード過程の最終的な状態。 新しいテナントの既定値でもあります。|
|アイランド|いずれか|いずれか|あり|既定の構成。 1 人のユーザーが両方のクライアントを並べて比較することができます。 チャットと通話はいずれかのクライアントに届くので、ユーザーは両方のクライアントを常に起動しておく必要があります。 Skype for Business エクスペリエンスが複雑化または低下することを回避するため、外部 (フェデレーション) コミュニケーション、PSTN 音声サービスと音声アプリケーション、Office の統合、その他のいくつかの統合は引き続き Skype for Business で処理されます。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|あり|"会議優先"。 主に、通話のクラウドへの移行準備ができていないオンプレミスの組織が、Teams 会議の機能を利用するためのものです。|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|はい|より緊密な管理制御を必要とする複雑な組織向けの、代替の開始地点。|
|SfBOnly|Skype for Business|Skype for Business|いいえ<sup>3</sup>|データ制御に関する厳密な要件が存在する組織向けの特殊なシナリオ。 Teams は、他のユーザーがスケジュールした会議に参加する場合にのみ使用します。|
||||||

</br>
</br>

**注:**

<sup>1</sup>既存の会議に参加する機能 (Teams または Skype for Business でスケジュールされている場合) は、モードによって管理されません。 既定では、ユーザーは常に招待されたすべての会議に参加できます。

<sup>2</sup> 既定では、個々のユーザーに TeamsOnly または SfbWithTeamsCollabAndMeetings を割り当てる場合、そのユーザーが将来予定している既存の Skype for Business 会議は Teams 会議に変換されます。 必要に応じて、TeamsUpgradePolicy を付与する際に `-MigrateMeetingsToTeams $false` を指定するか、Teams 管理ポータルのチェックボックスをオフにして、これらの会議を Skype for Business 会議として残すことができます。 TeamsUpgradePolicy をテナント全体に付与Skype for BusinessからTeamsに会議を変換する機能は使用できません。 

<sup>3</sup> Teams では現在、チームとチャンネル機能を無効にすることはできないため、今の段階では有効のままとなります。


## <a name="using-teamsupgradepolicy"></a>TeamsUpgradePolicy の使用

TeamsUpgradePolicy は、Mode と NotifySfbUsers の 2 つの主要プロパティを示しています。 
</br>
</br>

|パラメーター|型|使用できる値</br>(斜体が既定値)|説明|
|---|---|---|---|
|Mode|列挙|*アイランド*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|クライアントの実行モードを示します。|
|NotifySfbUsers|ブール|*false* または true|Skype for Business が間もなく Teams に置き換えられることをユーザーに知らせるバナーをクライアントに表示するかどうかを示します。 Mode=TeamsOnly の場合、これは true にできません。|
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
- ユーザー ($SipAddress) を Teamsするには、"UpgradeToTeams" インスタンスを付与します。</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- テナント全体をアップグレードするには、grant コマンドから Identity パラメーターを省略します。</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>新Teamsモードを使用する場合のクライアント ユーザー Skype for Businessエクスペリエンス

ユーザーが Skype for Business モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) に参加している場合、すべての着信チャットと呼び出しがユーザーの Skype for Business クライアントにルーティングされます。 エンド ユーザーの混乱を避け、適切なルーティングを確保するために、Teams クライアントの呼び出しとチャット機能は、ユーザーが Skype for Business モードに入っているときに自動的に無効になります。 同様に、Teams での会議のスケジュールも、ユーザーが SfBOnly モードまたは SfBWithTeamsCollab モードの場合は自動的に無効化され、ユーザーが SfBWithTeamsCollabAndMeetings モードの場合には自動的に有効化されます。 詳細については、「[Teams のクライアント エクスペリエンスおよび共存モードへの準拠](./teams-client-experience-and-conformance-to-coexistence-modes.md)」を参照してください。

> [!Note] 
> - Teams と Channels の自動適用を行う前に、SfbOnly と SfBWithTeamsCollab モードは同じように動作します。


## <a name="detailed-mode-descriptions"></a>モードの詳細な説明
</br>
</br>

|モード|説明|
|---|---|
|**アイランド**</br>(既定)|ユーザーは、Skype for BusinessとTeamsの両方を実行します。 このユーザーは、</br><ul><li>Skype for Business または Teams クライアントのいずれかでチャットと VoIP 通話を開始できます。 オンプレミスの Skype for Business に所属しているユーザーは、受信者のモードに関わらず、Teams から他の Skype for Business ユーザーに対して連絡することはできません。<li>他のユーザーが Skype for Business で開始したチャットと VoIP 通話を、自分の Skype for Business クライアントで受信します。<li>他のユーザーが Teams で開始したチャットと VoIP 通話を、そのユーザーが *同じテナント* にいる場合、自分の Teams クライアントで受信します。<li>他のユーザーが Teams で開始したチャットと VoIP 通話を、そのユーザーが *フェデレーションされたテナント* にいる場合、自分の Skype for Business クライアントで受信します。 <li>次に示すような、PSTN 機能があります。<ul><li>ユーザーがオンプレミスの Skype for Business に所属していてエンタープライズ VoIP を持っている場合、常に PSTN 通話が開始され、Skype for Business で受信されます。<li>ユーザーがオンプレミスの Skype for Business Online に所属していて Microsoft 電話システムを使用している場合、ユーザーは常に Skype for Business の PSTN 通話を開始および受信します。<ul><li>これは、ユーザーが Microsoft 通話プランを持っている場合でも、Skype for Business クラウド コネクタ エディション (ハイブリッド音声 Skype for Business Server) のオンプレミス 展開を介して PSTN ネットワークに接続する場合でも発生します。<li>**注: 電話システムルーティングは、諸島モードではサポートされていません。**</ul></ul><li>Skype for Business で Microsoft 通話キューと自動応答通話を受信します。<ul><li>電話と自動応答に割り当てられている番号は、電話システムモードでは直接ルーティング番号を使用できません。</ul></ul><li>Teams または Skype for Business で会議をスケジュールすることができます (また、既定では両方のプラグインが表示されます)。<li>Skype for Business または Teams のあらゆる会議に参加できます。会議はそれぞれのクライアントで開きます。</ul>|
|**SfBOnly**|ユーザーは Skype for Business のみを実行します。 このユーザーは、</br><ul><li>Skype for Business からのみチャットと通話を開始することができます。<li>オンプレミスの Skype for Business に所属している Teams ユーザーが開始したものでない限り、すべてのチャット/通話を開始元に関わらず自分の Skype for Business クライアントで受信します。*<li>Skype for Business の会議のみスケジュールできます。ただし、Skype for Business 会議と Teams 会議のいずれにも参加することができます。</br>\** オンプレミスのユーザーにアイランド モードを使用することは、他の SfBOnly モードのユーザーとの組み合わせにおいて、お勧めできません。 Teams を持つ Skype for Business を持つユーザーが SfBOnly ユーザーへの通話またはチャットを開始した場合、SfBOnly ユーザーは到達不能であり、チャットを見逃したり、メールを呼び出したりします。*|
|**SfBWithTeamsCollab**|ユーザーは、Skype for BusinessとTeamsの両方を実行します。 このユーザーは、</br><ul><li>SfBOnly モードのユーザーと同じ機能があります。<li>Teams をグループでの共同作業 (チャネル) に関してのみ利用できます。チャット/通話/会議のスケジュールは利用できません。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|ユーザーは、Skype for BusinessとTeamsの両方を実行します。 このユーザーは、<ul><li>SfBOnly モードのユーザーと同じチャットと通話機能があります。<li>Teams をグループでの共同作業 (チャネル (チャネル会話を含む)) に対してのみ利用できます。チャットと通話は利用できません。<li>Teams 会議のみスケジュールできます。ただし、Skype for Business 会議と Teams 会議のいずれにも参加することができます。</ul>|
|**TeamsOnly**</br>(Skype for Business Online に所属していることが必要)|ユーザーは Teams のみ実行します。 このユーザーは、<ul><li>すべてのチャットと通話を開始元に関わらず自分の Teams クライアントで受信します。<li>Teams からのみチャットと通話を開始することができます。<li>Teams でのみ会議をスケジュールできます。ただし、Skype for Business 会議と Teams 会議のいずれにも参加することができます。<li>Skype for Business IP 電話を使用し続けることができます。<br><br>*TeamsOnly モードを他のユーザーと諸島モードで組み合わせて使用Teamsは推奨されません。つまり、すべての Islands モードのユーザーは、アクティブなクライアントとTeamsとSkype for Businessします。TeamsOnly ユーザーが Islands ユーザーへの通話またはチャットを開始した場合、その通話またはチャットは Islands ユーザーの Teamsされます。Islands ユーザーがアカウントを使用または監視Teams、そのユーザーはオフラインで表示され、TeamsOnly ユーザーがアクセスできなくなります。*</ul> |
|||




## <a name="related-topics"></a>関連項目

[Skype for Business と共存する](./coexistence-chat-calls-presence.md)

[Teams のクライアント エクスペリエンスおよび共存モードへの準拠](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[Meeting Migration Service (MMS) の使用](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
