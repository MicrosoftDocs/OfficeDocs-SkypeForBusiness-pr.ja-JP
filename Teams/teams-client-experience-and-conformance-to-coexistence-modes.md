---
title: Teams のクライアント エクスペリエンスおよび共存モードへの準拠
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Teams クライアントのエクスペリエンスと共存モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) について学習します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20d1ff52fa59f31b796d2580a0e2819c80caaf42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821027"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams のクライアント エクスペリエンスおよび共存モードへの準拠

<a name="about-upgrade-basic"></a>

Skype for Business 共存モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) の目的は、組織が Skype for Business から Teams に移行する際に、シンプルで予測可能なエクスペリエンスをエンド ユーザーに提供することです。  Teams に移行する組織にとって、最終的にはすべてのユーザーを **TeamsOnly** モードにすることが目標ですが、**TeamsOnly** (またはその他のモード) を全員に同時に割り当てる必要はありません。  ユーザーが TeamsOnly モードに到達する前に、組織は Skype for Business の共存モードを使用して **、Teams のみ** であるユーザーとまだいないユーザーとの間で予測可能な通信を確保できます。 

ユーザーが Skype for Business モードの場合、すべての着信チャットと通話がユーザーの Skype for Business クライアントにルーティングされます。 ユーザーがいずれかの Skype for Business モードに設定されている場合、エンド ユーザーを混乱させない適切なルーティングを確保するために、Teams クライアントの通話とチャット機能は無効化されます。 同様に、Teams での会議のスケジュールも、ユーザーが SfBOnly または SfBWithTeamsCollab モードの場合は明示的に無効化され、ユーザーが SfBWithTeamsCollabAndMeetings の場合には明示的に有効化されます。

プレゼンスはチャットや通話を通じて到達可能性を示すので、チャットと通話が無効になっている場合、Teams での自己プレゼンス (つまり、ユーザーの写真の Teams クライアントでの自分のプレゼンスの表示) も非表示になります。 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Teams クライアントで使用可能な機能がモードによってどのように変化するか

Teams で使用できる機能は、TeamsUpgradePolicy で設定されているユーザーの共存モードによって異なります。 次の表は、動作をまとめたものです。

|ユーザーの有効なモード|Teams クライアントでのエクスペリエンス|
|---|---|
|任意の Skype for Business モード|通話、チャット、および自己プレゼンスは無効です。|
|SfBWithTeamsCollabAndMeetings|会議のスケジュールを利用できます|
|SfBWithTeamsCollab または SfBOnly<sup>1</sup>|会議のスケジュールは利用できません|
|||

次のスクリーンショットでは、**TeamsOnly** または **アイランド** モードと、その他のすべてのモードとの違いを示しています。 **TeamsOnly** または **アイランド** モード (左側のスクリーンショット) を使用する場合、既定ではチャットと通話のアイコンが表示されますが、他のモード (右のスクリーンショット) では表示されません。

![Teams モードを並べて比較](media/teams-mode-comparison.png)

また、次に示すように、他のモードでは自己プレゼンスを使用できません。

![会議を初めて利用したときの自己プレゼンスのスクリーンショット](media/meetings-first-no-self-presence-general.png)
 
**注:**
<sup>1</sup> 現時点では、SfBwithTeamsCollab と SfBOnly は同じように動作しますが、SfBOnly モードでは、Teams のチャネルとファイル機能も無効にします。 その間、アプリの権限ポリシーを使用してチャネルを非表示にできます。


## <a name="impact-of-mode-on-other-policy-settings"></a>他のポリシー設定に対するモードの影響
上記のように、ユーザーの共存モードは、ユーザーの Teams クライアントで使用可能な機能に影響を与えます。 つまり、モードによっては、モードの値が他のポリシー設定の値よりも優先される場合があります。 特に、共存モードは、次のポリシー設定が適用されるかどうかに影響します。

|**モダリティ (アプリ)**|**Policy.Setting**|
|---|---|
|チャット|TeamsMessagingPolicy.AllowUserChat|
|通話|TeamsCallingPolicy.AllowPrivateCalling|
|会議のスケジュール|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

共存モードを使用する場合、管理者はこれらのポリシー設定を明示的に設定する必要は *ありません* が、これらの設定は特定のモードに対して次のように効果的に動作することを理解することが重要です。 

|モード|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly または アイランド|有効|有効|有効|有効|
|SfBWithTeamsCollabAndMeetings|無効|無効|有効|有効|
|SfBWithTeamsCollab または SfBOnly|無効|無効|無効|無効|
||||||

PowerShell を使用する場合、`Grant-CsTeamsUpgradePolicy` コマンドレットは TeamsMessagingPolicy、TeamsCallingPolicy、および TeamsMeetingPolicy の対応する設定の構成を確認して、これらの設定が TeamsUpgradePolicy によって置き換えられるかどうかを判断し、そうであれば PowerShell で情報メッセージが提供されます。  上記のように、これらの他のポリシー設定を設定する必要はなくなりました。 次に、PowerShell の警告の例を示します。

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>関連項目

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




