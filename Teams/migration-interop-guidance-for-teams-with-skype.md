---
title: 移行と相互運用性-Skype for Business
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams への組織の移行を管理するための基本的な概念について説明します。
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
ms.openlocfilehash: c30877a9563a5f97cbe2b4a7d5b8b136d5ec9ebd
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940557"
---
# <a name="coexistence-modes---reference"></a>共存モード-参照

共存モードは、組織が Skype for Business から Teams に移行した場合に、エンドユーザーが簡単かつ予測可能なエクスペリエンスを提供します。 Teams に移行する組織にとって、各ユーザーの最終的な目的地は TeamsOnly モードですが、すべてのユーザーに TeamsOnly (またはその他のモード) を同時に割り当てる必要はありません。 ユーザーが TeamsOnly モードになる前は、Skype for Business モード (SfBOnly、Sfbwithteams、SfBWithTeamsCollabAndMeetings) のいずれかを使用して、teams のみで、かつまだ存在しないユーザー間で一貫した通信を行うことができます。

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


## <a name="using-teamsupgradepolicy"></a>TeamsUpgradePolicy を使用する

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

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>Skype for Business モードを使用している場合の Teams クライアントユーザーエクスペリエンス

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
