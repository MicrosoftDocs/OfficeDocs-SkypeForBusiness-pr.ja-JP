---
title: Teams のクライアント エクスペリエンスおよび共存モードへの準拠
author: dearbeen
ms.author: bjwhalen
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
ms.openlocfilehash: 6972a09a169560d255c2bb118f80dbbdfb2c7f4f
ms.sourcegitcommit: 8e5fc1d8c19a7f26f53e40b23dd6476a8c6d805f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2019
ms.locfileid: "30800133"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams のクライアント エクスペリエンスおよび共存モードへの準拠

> [!NOTE]
> このページは、ユーザーは、Skype のビジネス ・ モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) のいずれかで、時に、チームのクライアントの動作に重要な今後の変更点を説明します。


共存モードの目的は、エクスペリエンスを提供する単純かつ予測可能なエンド ・ ユーザーの組織の移行とビジネス用の Skype からのチームには。  チームに移動する組織、TeamsOnly モードは、各ユーザーの最終的な宛先を同時に TeamsOnly (または他のモード) に割り当てられる必要はないすべてのユーザーです。  ユーザーが TeamsOnly モードに到達する前に、組織は Skype for Business の任意のモード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) を使用して、TeamsOnly であるユーザーとまだ TeamsOnly ではないユーザー間の予測可能な通信を確保することができます。 

ユーザーは、Skype のビジネス モードのいずれかでは、ビジネスのクライアントのユーザーの Skype にすべての着信のチャットや通話がルーティングされます。 エンド ユーザーが混乱することを回避し、適切なルーティングを実現するため、Teams クライアントの通話とチャット機能は、ユーザーがいずれかの Skype for Business モードにある場合は無効になるように意図されています。 同様に、Teams での会議のスケジュールも、ユーザーが SfBOnly または SfBWithTeamsCollab モードの場合は明示的に無効になるように、そしてユーザーが SfBWithTeamsCollabAndMeetings の場合に明示的に有効になるように意図されています。  自動的に無効にする機能チャットし、機能を呼び出す会議のモードに基づいてスケジュール設定を有効または無効とは今すぐ開始タップの顧客に公開します。  

この機能では、前にマイクロソフトのガイダンスは、メッセージングの呼び出し、およびミーティングのポリシーに対応する設定を設定することによって適切なユーザー エクスペリエンスを確実にしました。 ただしの仮の強制がなかったし、チーム クライアント内のすべての機能へのフル アクセスがあるユーザーは既定であるため一部のユーザーでそのモードに関係なく、チーム クライアントでこれらのエクスペリエンスの一部またはすべてへのアクセスが保持している可能性があります。  その結果、この機能を発表と一部のユーザー可能性がありますを参照してくださいチーム クライアントで自分の経験では変更・ モードに準拠するようにユーザーの操作が開始されます。  次の表は、新しい動作を示しています。


|ユーザーの有効なモード|チームのクライアントで発生します。|
|---|---|
|ビジネス モードでは、Skype|通話とチャット<sup>1</sup>が無効になります。|
|SfBWithTeamsCollabAndMeetings|会議のスケジュール設定があります。|
|SfBWithTeamsCollab または SfBOnly の<sup>2</sup>|会議のスケジュール設定は使用できません。|
|||

**メモ:**
<sup>1</sup>会議チャットが利用できます。

<sup>2</sup>ここでは、SfBwithTeamsCollab と SfBOnly の動作は同じですが、SfBOnly モードでもチームでのチャネル、およびファイルの機能を無効にすることが目的ただし、設定されていない現在無効にするチームでこの機能を可能にします。


## <a name="how-organizations-can-prepare-for-automatic-ux-conformance-to-modes"></a>モード自動ユーザー エクスペリエンスへの準拠の組織をどのように準備することができます。

この変更を展開する前に組織は、このセクションで説明したように追加のポリシーを使用してチームのクライアントで必要なエクスペリエンスを実現できます。 これにより、展開では、エンド ・ ユーザーのシームレスです。 変更を発表、これらのポリシーを設定しないことを必要に注意してください。  同様のルーティングに影響をユーザーのチームのクライアントで機能が制限するためにしないようにしている組織は島モードを TeamsOnly モードでは、ユーザーを移動できます。

エンド ユーザー エクスペリエンスを手動で構成するには、管理者は、以下のポリシー設定を使用します。


|**モーダルかどうか (アプリケーション)**|**Policy.Setting**|
|---|---|
|チャット|TeamsMessagingPolicy.AllowUserChat|
|通話|TeamsCallingPolicy.AllowPrivateCalling|
|会議のスケジュール|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||


管理者は、特定のモードには、次の値にこれらの設定を設定する必要があります。

|Mode|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly または諸島|有効|有効|有効|有効|
|SfBWithTeamsCollabAndMeetings|無効|無効|有効|有効|
|SfBWithTeamsCollab または SfBOnly|無効|無効|無効|無効|
||||||

モードに基づいてユーザー エクスペリエンスの自動準拠のロールアウトする前に、`Grant-CsTeamsUpgradePolicy`コマンドレットの場合は、これらを決定するには、TeamsMessagingPolicy、TeamsCallingPolicy、および TeamsMeetingPolicy に対応する設定の構成をチェックします。設定は、指定したモードと互換性があります。 いずれかが正しく構成されていません場合、は、補助金は成功しますが、警告が行われます PowerShell でどの特定の設定が正しく構成されていないことを示します。 以下のようになりますが、PowerShell の警告の例に示します。

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has effective policy enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the near term, when granting TeamsUpgradePolicy with mode=SfBWithTeamsCollab to a user, you must also separately assign policy to ensure the user has effective policy disabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the future, the capability will automatically honor TeamsUpgradePolicy.`

このような警告を表示するには、時に、管理者はチームで互換性のあるエンド ユーザー エクスペリエンスを提供するのには示されているポリシーを後で更新する必要があります。 管理者が警告の結果として何も対応しないことを決めた場合でも、TeamsMessagingPolicy、TeamsCallingPolicy、TeamsMeetingPolicy の値に応じて、ユーザーは Teams のチャット、通話、会議スケジュール機能を利用できますが、エンド ユーザー エクスペリエンスがわかりにくくなる可能性があります。

TeamsUpgradePolicy モードに基づくチーム クライアント エクスペリエンスの自動適合性が利用できると、不要になった必要がありますこれらのポリシーを設定します。 TeamsUpgradePolicy モードの値が優先されますこれらの特定の設定の値をします。 自動準拠は、ポリシーの解決中にポリシーのインフラストラクチャで実現します。 さまざまな設定の競合が発生した場合は、AllowUserChat、AllowPrivateCalling、AllowPrivateMeetingScheduling および AllowChannelMeetingScheduling の値をモードに基づいた動作が優先されます。 自動適合性を提供すると後、は、クライアント エクスペリエンスが自動的に適用される、TeamsMessagingPolicy、TeamsCallingPolicy、および TeamsMeetingPolicy の値にかかわらず、管理者に通知する PowerShell の警告が更新されます。







