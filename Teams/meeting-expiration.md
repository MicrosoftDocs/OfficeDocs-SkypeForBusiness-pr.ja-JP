---
title: 会議ポリシーと会議の有効期限 (Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: 会議ポリシー設定を使用して、会議の有効期限を制御する方法についてMicrosoft Teams。
ms.openlocfilehash: e201348ba1734539844a76b0fee2e2f072757e87
ms.sourcegitcommit: 1c5608e6b539e90e42f48212d038f861ecf8136b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53337816"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>会議ポリシーと会議の有効期限 (Microsoft Teams

[](meeting-policies-in-teams.md) Microsoft Teams の会議ポリシーは、組織内のユーザーが会議を開始およびスケジュールできるかどうかと、ユーザーがスケジュールした会議に対して会議参加者が使用できる機能を制御するために使用されます。 グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。 Microsoft Teams 管理センターで、または Get [、New、Set、Remove、Grant](/powershell/module/skype/new-csteamsmeetingpolicy)-CsTeamsMeetingPolicy PowerShell コマンドレットを使用して、会議ポリシーを管理します。 [](/powershell/module/skype/get-csteamsmeetingpolicy) [](/powershell/module/skype/set-csteamsmeetingpolicy) [](/powershell/module/skype/remove-csteamsmeetingpolicy) [](/powershell/module/skype/grant-csteamsmeetingpolicy)

ユーザーが会議を開始およびスケジュールできるかどうかを制御し、ユーザーがスケジュールした会議の有効期限を制御する会議ポリシー設定。 会議の参加リンクと会議 ID の有効期限が切れると、誰も会議に参加できます。 次の会議ポリシー設定は、ユーザーが会議を開始してスケジュールできるかどうかを決定Teams。 この記事では、会議の設定について説明します。

- [[チャネルで今すぐ](meeting-policies-in-teams-general.md#allow-meet-now-in-channels)会議を許可する]: ユーザーがチャネルで一時会議を開始できるかどうかを制御します。
- [チャネル会議のスケジュール設定](meeting-policies-in-teams-general.md#allow-channel-meeting-scheduling)を許可する: ユーザーがチャネルで会議をスケジュールできるかどうかを制御します。
- [[プライベート会議のスケジュール設定](meeting-policies-in-teams-general.md#allow-scheduling-private-meetings)を許可する]: ユーザーが会議中にプライベート会議をスケジュールTeams。 チームのチャネルに公開されていない会議はプライベートです。
- [[追加を許可Outlook:](meeting-policies-in-teams-general.md#allow-the-outlook-add-in)ユーザーが会議からプライベート会議をスケジュールできるかどうかをOutlook。 チームのチャネルに公開されていない会議はプライベートです。
- [[プライベート会議で今すぐ](meeting-policies-in-teams-general.md#allow-meet-now-in-private-meetings)会議を許可する]: ユーザーが一時プライベート会議を開始できるかどうかを制御します。

既定では、これらの設定はオンになっています。 これらの設定が無効になっている場合、ポリシーが割り当てられているユーザーは、その種類の新しい会議を開始またはスケジュール設定できます。 同時に、ユーザーが以前に開始またはスケジュールした、その種類のすべての既存の会議の会議参加リンクと会議 ID が期限切れになります。

たとえば、これらの会議ポリシー設定が **[** オン] に設定されている会議ポリシーがユーザーに割り当てられている場合、[チャネルで今すぐ会議を許可する] 設定をオフにすると、そのユーザーはチャネルで即日会議を開始できなくなりました。また、[会議] チャネルでは、以前に作成したリンクが期限切れになります。 ユーザーは、他の種類の会議を開始してスケジュールを設定し、他のユーザーが開催した会議に参加できます。

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>会議参加リンクと会議 ID の有効期限が切れると、どうなるでしょうか。

会議の参加リンクと会議 ID の有効期限が切れると、誰も会議に参加できます。 ユーザーがリンクまたは電話で会議に参加しようとすると、会議が利用できなくなったというメッセージが表示されます。 会話、ファイル、ホワイトボード、レコーディング、トランスクリプト、会議に関連するその他のコンテンツは保持され、ユーザーは引き続きアクセスできます。

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>会議ポリシー設定をオンまたはオフにすると、何が起こりますか?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>会議ポリシー設定をオンからオフに切り替える

会議ポリシー設定が [オン]に設定されている場合、ポリシーが割り当てられているユーザーは、その種類の会議を開始またはスケジュールできます。すべてのユーザーが参加できます。 会議ポリシー設定を **[** オフ] に切り替えた場合、ポリシーが割り当てられているユーザーは、その種類の新しい会議を開始またはスケジュールできないので、ユーザーが以前にスケジュールした既存の会議の会議参加リンクと会議 ID が期限切れになります。

ユーザーは、他のユーザーが開催した会議に引き続き参加できます。

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>会議ポリシー設定をオフからオンに切り替える

会議ポリシー設定を [オフ]から **[オン**] に切り替える場合、ポリシーが割り当てられているユーザーは、その種類の会議を開始またはスケジュールできます。 ユーザーに対して会議ポリシー設定がオフになってから再び有効にした場合、ユーザーが開催した以前にスケジュールされた会議 (および期限切れ) はすべてアクティブになり、ユーザーは会議参加リンクまたは電話を使用して会議に参加できます。  

## <a name="meeting-expiration-scenarios"></a>会議の有効期限のシナリオ

この記事で説明する各会議ポリシー設定について、会議の有効期限のしくみの概要を次に示します。

|必要な場合...&nbsp;&nbsp; |これを行う&nbsp;&nbsp;&nbsp;&nbsp;  |会議参加の動作&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|ユーザーが開始したプライベート会議の有効期限を切る&nbsp;&nbsp;|プライベート会議 **で [今すぐ会議を許可する] をオフにします**。&nbsp;&nbsp;|ユーザーが開始した **プライベート会議に** 誰も参加できます。|
|ユーザーがスケジュールしたプライベート会議の有効期限を切る&nbsp;&nbsp;|[プライベート **会議のスケジュール設定を許可する**]_をオフに_ し、[Allow the **Outlook アドインを許可する] をオフにします**。 &nbsp;&nbsp;|ユーザーがスケジュールした非公開の会議に誰も参加できます。 これにより、ユーザーは次の会議に参加できます。<ul><li>過去に発生したプライベート会議。</li><li>将来予定され、まだ発生していないプライベート会議。</li><li>定期的なプライベート会議の今後のインスタンス。</li></ul><br>[**プライベート会議のスケジュール** 設定を許可する]**と [Outlook** を許可する] の両方をオフにし、ユーザーがスケジュールしたプライベート会議を期限切れにする必要があります。 1 つの設定がオフで、もう 1 つの設定がオンになっている場合、既存の会議の会議参加リンクと会議の数はアクティブなままであり、有効期限が切れはされません。|
|期限切れチャネル **ユーザーが開始** した会議を今すぐ満たす&nbsp;&nbsp;|チャネルで **[今すぐ会議を許可する] をオフにし**_、[_ チャネル会議 **のスケジュールを許可する] をオフにします**。&nbsp;&nbsp;|ユーザーが開始した [ **今すぐ会議]** チャネルに参加できるユーザーはいます。|
|ユーザーがスケジュールしたチャネル会議の有効期限を切る&nbsp;&nbsp;|[チャネル会議 **のスケジュール設定を許可する] をオフにします**。&nbsp;&nbsp;|ユーザーがスケジュールしたチャネル会議に誰も参加できます。 これにより、ユーザーは次の会議に参加できます。<ul><li>過去に発生したチャネル会議。</li><li>将来予定され、まだ発生していないチャネル会議。</li><li>定期的なチャネル会議の今後のインスタンス。</li></ul>|

特定のユーザーが以前にスケジュールまたは開始した会議にユーザーがアクセスする場合は、次の方法があります。

- そのユーザーの会議ポリシー設定を有効にします。
- そのユーザーの会議ポリシー設定をオフにし、ポリシー設定を有効にしている別のユーザーに、期限切れの会議を置き換える新しい会議を作成します。

> [!NOTE]
> 会議が代理人によって送信された場合(管理者など、他のユーザーの代わりに会議出席依頼を送信するアクセス許可が与えられた場合)、会議ポリシー設定は、アクセス許可を付与したユーザー (マネージャー) に適用されます。

## <a name="related-topics"></a>関連項目

[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)

[ Teams でユーザーにポリシーを割り当てる](assign-policies.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)
