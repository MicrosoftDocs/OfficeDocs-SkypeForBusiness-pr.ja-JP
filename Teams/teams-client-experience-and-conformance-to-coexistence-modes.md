---
title: Teams のクライアント エクスペリエンスおよび共存モードへの準拠
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Teams のクライアント エクスペリエンスおよび共存モードへの準拠
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e05a95871dbe36f969c048f32d9bca99fec5d45
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435241"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams のクライアント エクスペリエンスおよび共存モードへの準拠


Skype for Business の共存モード (SfBOnly、Sfbwithteams での共同作業、SfBWithTeamsCollabAndMeetings) の目的は、エンドユーザーが Skype for Business からチームに移行するときに、簡単で予測可能なエクスペリエンスを提供することです。  チームに移行する組織の場合、**チームのみ**のモードは各ユーザーの最終的な送信先ですが、すべてのユーザーが**チームのみ**(または他のモード) に同時に割り当てる必要はありません。  ユーザーが Teams の唯一のモードに到達する前に、組織は Skype for Business の共存モードのいずれかを使用して、**チームのみ**で、かつまだお持ちではないユーザー間で一貫した通信を行うことができます。 

ユーザーが Skype for Business モードのいずれかに入っている場合、着信するすべてのチャットと通話はユーザーの Skype for Business クライアントにルーティングされます。 ユーザーが Skype for Business モードのいずれかを使用している場合、エンドユーザーの混乱を回避して、適切なルーティング、チームクライアントの通話、チャット機能を無効にすることができます。 同様に、Teams での会議のスケジュール設定は、ユーザーが SfBOnly または Sfbwithteams・ SfBWithTeamsCollabAndMeetings モードになっているときに明示的に無効にし、ユーザーがモードにあるときに明示的に有効にします。

プレゼンスはチャットと通話での到達可能性を示しているため、チャットや通話が無効になっていると、Teams での自己プレゼンス (つまり、ユーザーの写真の Teams クライアントでの1つのプレゼンスの表示) も非表示になります。 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>チームクライアントで利用できる機能がモードに基づいてどのように変化するか

Teams で利用できる機能は、TeamsUpgradePolicy によって設定されるユーザーの共存モードによって異なります。 次の表は、この動作をまとめたものです。

|ユーザーの有効モード|Teams クライアントでの操作|
|---|---|
|任意の Skype for Business モード|通話、チャット、および自己プレゼンスは無効になります。|
|SfBWithTeamsCollabAndMeetings|会議のスケジュールを使用できます|
|Sfbwithteamsの小条件<sup>1</sup>または Sfbのみ|会議のスケジュールを使用できない|
|||

次のスクリーンショットは、 **Teams**モードとその他のすべて**のモードの**違いを示しています。 チャットと通話のアイコンは、既定では、 **Teams のみ**または**諸島**モード (左のスクリーンショット) で利用できますが、他のモード (右のスクリーンショット) では使用できません。

![Teams のモードの並列比較](media/teams-mode-comparison.png)

さらに、次に示すように、他のモードでは自己プレゼンスは使用できません。

![最初に会議の自分のプレゼンスのスクリーンショット](media/meetings-first-no-self-presence-general.png)
 
**注:**
この時点では、sfbwithteamscollab と sfbonly は<sup>同じように</sup>動作しますが、sfbonly モードの場合は、Teams のチャネルとファイルの機能も無効にします。 中間では、アプリのアクセス許可ポリシーを使ってチャネルを非表示にすることができます。


## <a name="impact-of-mode-on-other-policy-settings"></a>他のポリシー設定でのモードの影響
上で説明したように、ユーザーの共存モードの影響は、ユーザーのチームクライアントで利用できる機能です。 これは、モードに応じて、他のポリシー設定の値よりもモードの値が優先されることを意味します。 特に、共存モードでは、次のポリシー設定が有効になっているかどうかが影響を受けます。

|**モダリティ (アプリ)**|**ポリシー。設定**|
|---|---|
|チャット|Teams の Messagingポリシー AllowUserChat|
|通話|TeamAllowPrivateCalling|
|会議のスケジュール|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy の会議のスケジュール|
|||

管理者は、共存モードの使用時にこれらのポリシー設定を明示的に設定する必要はあり*ません*が、これらの設定が特定のモードで次のように効率的に動作することを理解しておくことが重要です。 

|Mode|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|Allowchannel会議のスケジュール|
|---|---|---|---|---|
|TeamsOnly または諸島|有効|有効|有効|有効|
|SfBWithTeamsCollabAndMeetings|無効|無効|有効|有効|
|Sfbwithteamsの各アシスタントまたは Sfbのみ|無効|無効|無効|無効|
||||||

PowerShell を使用して`Grant-CsTeamsUpgradePolicy`いる場合、コマンドレットは、TeamsMessagingPolicy、TeamTeamsMeetingPolicy のポリシー、およびの対応する設定の構成を確認し、それらの設定が TeamsUpgradePolicy によって置き換えられるかどうかを判断します。情報メッセージは PowerShell で提供されます。  上記で説明したように、他のポリシー設定を設定する必要はありません。 次に示すのは、PowerShell の警告の例です。

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>関連トピック

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




