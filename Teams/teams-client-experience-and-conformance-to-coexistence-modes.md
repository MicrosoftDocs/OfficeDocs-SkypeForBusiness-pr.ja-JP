---
title: Teams のクライアント エクスペリエンスおよび共存モードへの準拠
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: クライアント エクスペリエンスのチームとの共存モードに comformance
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91a67c7fb9afb5633494815129d141d5a08708d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930343"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams のクライアント エクスペリエンスおよび共存モードへの準拠

> [!NOTE]
> このページは、ユーザーは、Skype のビジネス ・ モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) のいずれかで、時に、チームのクライアントの動作で、最近リリースされた重要な変更の内容を説明します。


共存モードの目的は、エクスペリエンスを提供する単純かつ予測可能なエンド ・ ユーザーの組織の移行とビジネス用の Skype からのチームには。  チームに移動する組織、TeamsOnly モードは、各ユーザーの最終的な宛先を同時に TeamsOnly (または他のモード) に割り当てられる必要はないすべてのユーザーです。  ユーザーが TeamsOnly モードに到達する前に、組織は Skype for Business の任意のモード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) を使用して、TeamsOnly であるユーザーとまだ TeamsOnly ではないユーザー間の予測可能な通信を確保することができます。 

ユーザーは、Skype のビジネス モードのいずれかでは、ビジネスのクライアントのユーザーの Skype にすべての着信のチャットや通話がルーティングされます。 エンド ・ ユーザーの混乱を防止し、適切なルーティングを確保する、ユーザーは、Skype のビジネス モードのいずれかで、チームのクライアントでの通話やチャットの機能が無効になります。 同様に、チームでミーティングのスケジュール設定は SfBOnly または SfBWithTeamsCollab モードでは、ユーザーがいる場合は明示的に無効になってし、SfBWithTeamsCollabAndMeetings モードでは、ユーザーとを明示的に有効にします。   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>モードに基づくチームのクライアントで利用可能な機能がどのように変化するか
チームで利用可能な機能は、TeamsUpgradePolicy によって設定されるユーザーの共存モードとは異なります。 次の表は、動作をまとめたものです。

|ユーザーの有効なモード|チームのクライアントで発生します。|
|---|---|
|ビジネス モードでは、Skype|通話とチャットが無効になります。|
|SfBWithTeamsCollabAndMeetings|会議のスケジュール設定があります。|
|SfBWithTeamsCollab または SfBOnly<sup>1</sup>|会議のスケジュール設定は使用できません。|
|||

次のスクリーン ショットは、TeamsOnly または島のモードとその他のすべてのモードの違いを示しています。 チャットと通話のアイコンは、TeamsOnly または島モード (スクリーン ショットを左)、しない場合は、その他のモード (右のスクリーン ショット) で使用に注意してください。

![チーム モードの比較を示しています。](media/teams-mode-comparison.png)


 
**注:**
ここでは、SfBwithTeamsCollab と SfBOnly<sup>1</sup>の動作は同じですが、SfBOnly モードでもチームでのチャネル、およびファイルの機能を無効にすることが目的ただし、設定されていない現在無効にするチームでこの機能を可能にします。


## <a name="impact-of-mode-on-other-policy-settings"></a>モードの他のポリシー設定への影響
前述のとおり、ユーザーの共存モードへの影響は、ユーザーのチームのクライアントでどのような機能があります。 これは、あるモードの値が優先モードによって、他のポリシー設定の値を意味します。 具体的には、共存モードは、次のポリシー設定を有効にするかどうか影響します。

|**モーダルかどうか (アプリケーション)**|**Policy.Setting**|
|---|---|
|チャット|TeamsMessagingPolicy.AllowUserChat|
|通話|TeamsCallingPolicy.AllowPrivateCalling|
|会議のスケジュール|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

管理者が必要*ない*共存モードが、それが重要であるこれらの設定効果的に動作する次のように特定のモードを理解するときにこれらのポリシー設定を明示的に設定します。 

|Mode|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly または諸島|有効|有効|有効|有効|
|SfBWithTeamsCollabAndMeetings|無効|無効|有効|有効|
|SfBWithTeamsCollab または SfBOnly|無効|無効|無効|無効|
||||||

PowerShell を使用する場合、`Grant-CsTeamsUpgradePolicy`コマンドレットは、これらの設定は、TeamsUpgradePolicy によって上書きされますが、その場合を決定するには、TeamsMessagingPolicy、TeamsCallingPolicy、および TeamsMeetingPolicy に対応する設定の構成を確認します。PowerShell では、情報メッセージが提供されます。  上記で述べたようにこれらのポリシー設定を設定する必要はありません。 以下には、次のようにどのような PowerShell の警告の例を示します。

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>関連トピック

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




