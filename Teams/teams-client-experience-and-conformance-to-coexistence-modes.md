---
title: Teams のクライアント エクスペリエンスおよび共存モードへの準拠
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Teams のクライアントエクスペリエンスと comformance の共存モード
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08bc09ac316a41dfe7ff39bc741dbaa514f30044
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548654"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams のクライアント エクスペリエンスおよび共存モードへの準拠

> [!NOTE]
> このページでは、ユーザーが Skype for Business モード (SfBOnly、Sfbwithteams、SfBWithTeamsCollabAndMeetings) に参加しているときに、Teams クライアントの動作について最近公開された重要な変更点について説明します。


共存モードの目的は、組織が Skype for Business から Teams に移行するときに、エンドユーザーが簡単で予測可能なエクスペリエンスを提供することです。  チームに移行する組織の場合、Teams Sonly モードは各ユーザーの最終的な送信先です。ただし、すべてのユーザーが同時に Teams Sonly (または他のモード) を割り当てる必要はありません。  ユーザーが TeamsOnly モードに到達する前に、組織は Skype for Business の任意のモード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) を使用して、TeamsOnly であるユーザーとまだ TeamsOnly ではないユーザー間の予測可能な通信を確保することができます。 

ユーザーが Skype for Business モードのいずれかに入っている場合、着信するすべてのチャットと通話はユーザーの Skype for Business クライアントにルーティングされます。 ユーザーが Skype for Business モードのいずれかを使用している場合、エンドユーザーの混乱を回避して、適切なルーティング、チームクライアントの通話、チャット機能を無効にすることができます。 同様に、Teams での会議のスケジュール設定は、ユーザーが SfBOnly または Sfbwithteams・ SfBWithTeamsCollabAndMeetings モードになっているときに明示的に無効にし、ユーザーがモードにあるときに明示的に有効にします。   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>チームクライアントで利用できる機能がモードに基づいてどのように変化するか
Teams で利用できる機能は、TeamsUpgradePolicy によって設定されるユーザーの共存モードによって異なります。 次の表は、動作をまとめたものです。

|ユーザーの有効モード|Teams クライアントでの操作|
|---|---|
|任意の Skype for Business モード|通話とチャットは使用できません。|
|SfBWithTeamsCollabAndMeetings|会議のスケジュールを使用できます|
|Sfbwithteamsの小条件<sup>1</sup>または Sfbのみ|会議のスケジュールを使用できない|
|||

次のスクリーンショットは、TeamsOnly モードとその他のすべてのモードの違いを示しています。 チャットと通話のアイコンは、TeamsOnly または諸島モード (左のスクリーンショット) で利用できますが、その他のモード (右のスクリーンショット) では使用できません。

![Teams のモードの並列比較](media/teams-mode-comparison.png)


 
**注:**
<sup></sup>現時点では、sfbwithteamscollab と sfbは同じように動作しますが、sfbonly モードの場合は、Teams のチャネルとファイルの機能も無効にすることを目的としています。ただし、現在のところ、Teams でこの機能を無効にできる設定はありません。


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

PowerShell を使用して`Grant-CsTeamsUpgradePolicy`いる場合、コマンドレットは、TeamsMessagingPolicy、TeamTeamsMeetingPolicy のポリシー、およびの対応する設定の構成を確認し、それらの設定が TeamsUpgradePolicy によって置き換えられるかどうかを判断します。情報メッセージは PowerShell で提供されます。  上記で説明したように、他のポリシー設定を設定する必要はありません。 以下に、PowerShell の警告の例を示します。

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>関連トピック

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




