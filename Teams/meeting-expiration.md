---
title: Microsoft Teams での会議ポリシーと会議の有効期限
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Microsoft Teams で会議のポリシー設定を使用して、会議の有効期限を管理する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e25ea1c55890a78e9e492dd2c2dd419a6ed34f2
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640990"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Microsoft Teams での会議ポリシーと会議の有効期限

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>概要

Microsoft Teams の[会議ポリシー](meeting-policies-in-teams.md)は、組織内のユーザーが会議を開始してスケジュールできるかどうかを制御するために使用されます。また、ユーザーによってスケジュールされた会議の参加者に対して使用できる機能を管理することもできます。 グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。 会議ポリシーを管理するには、Microsoft Teams 管理センターで、または[Get](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy)、 [New](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)、 [Set](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)、 [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy)、 [Grant](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell コマンドレットを使用します。

ユーザーが会議を開始およびスケジュールするかどうかを制御する会議ポリシー設定では、ユーザーによってスケジュールされた会議の有効期限を管理することもできます。 会議の参加リンクと会議 ID の有効期限が切れた場合、だれも会議に参加できません。 以下の会議ポリシー設定では、ユーザーが Teams で会議を開始してスケジュールすることができるかどうかを決定します。この記事では、これらの設定について説明します。

- [[チャネルの今すぐ会議を許可する](meeting-policies-in-teams.md#allow-meet-now-in-channels)]: ユーザーがチャネルで一時的会議を開始できるかどうかを制御します。
- [チャネル会議のスケジュールの許可](meeting-policies-in-teams.md#allow-channel-meeting-scheduling): ユーザーがチャネルで会議をスケジュールできるかどうかを制御します。
- [プライベート会議のスケジュールを許可する](meeting-policies-in-teams.md#allow-scheduling-private-meetings): ユーザーが Teams でプライベート会議をスケジュールできるかどうかを制御します。 チームのチャネルに公開されていない会議はプライベートです。
- [Outlook の [アドインの許可](meeting-policies-in-teams.md#allow-the-outlook-add-in)]: ユーザーが outlook からプライベート会議をスケジュールできるかどうかを制御します。 チームのチャネルに公開されていない会議はプライベートです。
- [プライベート会議で今すぐ会議を許可する](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings): ユーザーが一時的プライベート会議を開始できるかどうかを制御します。

既定では、これらの設定はオンになっています。 これらの設定のいずれかをオフにすると、ポリシーが割り当てられたすべてのユーザーは、その種類の新しい会議を開始またはスケジュールすることはできません。 同時に、ユーザーが以前に開始またはスケジュールした、その種類の既存のすべての会議のリンクと会議 Id が、会議に参加することになります。

たとえば、これらの会議ポリシー設定が **[オン**] に設定されている会議ポリシーが割り当てられている場合、[**チャネルで今すぐ会議を許可**する] 設定をオフにすると、ユーザーはチャネル内で一時的の会議を開始できなくなり、ユーザーが以前作成したユーザーが以前作成した参加リンクが期限切れになります。 ユーザーは、他の種類の会議を開始してスケジュールすることができ、他のユーザーが開催した会議に参加することもできます。

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>会議の参加リンクと会議 ID の有効期限が切れるとどうなりますか?

会議の参加リンクと会議 ID の有効期限が切れると、だれも会議に参加できなくなります。 ユーザーがリンクまたは電話で会議に参加しようとすると、会議が利用できなくなったというメッセージが表示されます。 会話、ファイル、ホワイトボード、レコーディング、トランスクリプト、および会議に関連するその他のコンテンツは保持され、ユーザーはそれにアクセスできます。

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>会議のポリシー設定をオンにしてオフにするとどうなりますか?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>会議のポリシー設定を [オン] から [オフ] に切り替える

会議のポリシー設定が **[オン**] に設定されている場合、そのポリシーを割り当てられたユーザーは、その種類の会議を開始またはスケジュールすることができ、全員が参加できます。 会議のポリシー設定を [**オフ**] に切り替えると、ポリシーが割り当てられたユーザーは、その種類の新しい会議を開始またはスケジュールすることができません。また、ユーザーが以前スケジュールした既存の会議の会議の参加リンクと会議 id は期限切れになります。

ユーザーは、他のユーザーによって開催された会議にも参加できることに注意してください。

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>会議のポリシー設定を [オフ] から [オン] に切り替える

会議のポリシー設定を [**オフ**] から **[オン**] に切り替えると、そのポリシーを割り当てられたユーザーは、その種類の会議を開始またはスケジュールすることができます。 会議のポリシー設定を無効にして、ユーザーに対して再び有効にした場合、ユーザーによって開催されたすべてのスケジュールされた (有効期限が切れた) 会議がアクティブになり、参加者は [会議参加] リンクまたは [電話] を使って参加できます。  

## <a name="meeting-expiration-scenarios"></a>会議の有効期限のシナリオ

ここでは、この記事で説明されている各会議ポリシーの設定に対して、会議の有効期限がどのようになるかについて概要を示します。 

|必要な場合 |操作  |会議の参加の動作  |
|---------|---------|---------|
|ユーザーが開始した、チャネルの有効期限切れの会議  |**[チャネルでの会議の開始を許可する] を**オフにします。|ユーザーによって開始されたチャネルの会議に参加することはできません。         |
|ユーザーによってスケジュールされた、有効期限が切れたチャネル会議   |**チャネル会議のスケジュールの許可**を無効にします。         |ユーザーによってスケジュールされたチャネル会議に誰も参加することはできません。 これにより、ユーザーが次のように参加できなくなります。<ul><li>過去に発生した会議のチャネル。</li> <li>今後スケジュールされていて、まだ行われていない会議のチャネル。</li><li>今後の定期的なチャネル会議のインスタンス。</li></ul>       |
|ユーザーによってスケジュールされたプライベート会議の有効期限を設定する    |[**プライベート会議のスケジュールを許可する**] をオフに*して* **、[Outlook アドインの許可**] をオフにします。          |ユーザーによってスケジュールされたプライベート会議に誰も参加することはできません。 これにより、ユーザーが次のように参加できなくなります。 <ul><li>過去に発生したプライベート会議。</li> <li>今後スケジュールされていて、まだ行われていないプライベートな会議。</li><li>今後の定期的なプライベート会議のインスタンス。</li></ul> どちらの場合も、**プライベート会議のスケジュールを設定**し、 **Outlook アドイン**をオフにして、ユーザーによってスケジュールされたプライベート会議を有効にする必要があります。 1つの設定がオフで、もう一方がオンになっている場合、会議の参加リンクと既存の会議の会議 Id は有効なままになり、期限切れになりません。      |
|ユーザーが開始したプライベート会議の有効期限の終了  |**[プライベート会議で今すぐ会議を許可する] を**オフにします。          |ユーザによって開始されたプライベート会議 now 会議には誰も参加できません。         |

特定のユーザーによって以前にスケジュールまたは開始された会議に他のユーザーがアクセスできるようにするには、次の操作を行います。

- そのユーザーの会議のポリシー設定をオンにします。
- そのユーザーの会議のポリシー設定を無効にし、そのポリシー設定を有効にしている別のユーザーに新しい会議を作成して、期限切れの会議を置き換えます。

> [!NOTE]
> 会議が代理人によって送信され、上司などの他のユーザーの代わりに会議出席依頼を送信する権限が与えられている場合、会議のポリシー設定は、アクセス許可を付与したユーザー (上司) に適用されます。

## <a name="related-topics"></a>関連項目

[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)

[チームのユーザーにポリシーを割り当てる](assign-policies.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)