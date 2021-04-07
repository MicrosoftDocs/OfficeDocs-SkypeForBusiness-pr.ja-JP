---
title: Microsoft Teams の会議ポリシーと会議の有効期限
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
description: Microsoft Teams で会議ポリシー設定を使用して会議の有効期限を制御する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6e8821781eab70696c9b24c8df18cc8dd0b46870
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598616"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Microsoft Teams の会議ポリシーと会議の有効期限

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>概要

Microsoft Teams[の](meeting-policies-in-teams.md)会議ポリシーは、組織内のユーザーが会議を開始およびスケジュールできるかどうか、およびユーザーがスケジュールした会議の会議参加者が使用できる機能を制御するために使用されます。 グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。 Microsoft Teams 管理センターで、または Get、New、Set、Remove、Grant [](/powershell/module/skype/remove-csteamsmeetingpolicy)-CsTeamsMeetingPolicy PowerShell コマンドレットを使用して、会議ポリシーを管理します。 [](/powershell/module/skype/get-csteamsmeetingpolicy) [](/powershell/module/skype/new-csteamsmeetingpolicy) [](/powershell/module/skype/set-csteamsmeetingpolicy) [](/powershell/module/skype/grant-csteamsmeetingpolicy)

ユーザーが会議を開始およびスケジュールできるかどうかを制御する会議ポリシー設定は、ユーザーがスケジュールした会議の有効期限も制御します。 会議への参加リンクと会議 ID の有効期限が切れると、誰も会議に参加できます。 次の会議ポリシー設定では、ユーザーが Teams で会議を開始およびスケジュールできるかどうかを決定します。この記事全体でそれらを参照しています。

- [チャネルで今すぐ会議を](meeting-policies-in-teams-general.md#allow-meet-now-in-channels)許可する: ユーザーがチャネルで一時会議を開始できるかどうかを制御します。
- [チャネル会議のスケジュールを](meeting-policies-in-teams-general.md#allow-channel-meeting-scheduling)許可する: ユーザーがチャネルで会議をスケジュールできるかどうかを制御します。
- [プライベート会議のスケジュール設定](meeting-policies-in-teams-general.md#allow-scheduling-private-meetings)を許可する: ユーザーが Teams でプライベート会議をスケジュールできるかどうかを制御します。 チームのチャネルに公開されていない会議はプライベートです。
- [Outlook の追加を許可](meeting-policies-in-teams-general.md#allow-the-outlook-add-in)する: ユーザーが Outlook からプライベート会議をスケジュールできるかどうかを制御します。 チームのチャネルに公開されていない会議はプライベートです。
- [プライベート会議で今すぐ会議を](meeting-policies-in-teams-general.md#allow-meet-now-in-private-meetings)許可する: ユーザーが一時プライベート会議を開始できるかどうかを制御します。

既定では、これらの設定はオンになっています。 これらの設定をオフにすると、ポリシーが割り当てられたユーザーは、その種類の新しい会議を開始したり、スケジュールしたりできない。 同時に、ユーザーが以前に開始またはスケジュールした、その種類のすべての既存の会議のリンクと会議 ID も会議に参加します。

たとえば、ユーザーに会議ポリシー設定が [オン] に設定されている会議ポリシーが割り当てられている場合、[チャネルで今すぐ会議を許可する] 設定をオフにすると、そのユーザーはチャネルで一時会議を開始できなくなりました。チャネル [会議] は、以前に作成したリンクに参加すると期限切れになります。 ユーザーは、他の種類の会議を開始してスケジュールを設定し、他のユーザーが開催した会議に参加できます。

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>会議参加リンクと会議 ID の有効期限が切れた場合

会議への参加リンクと会議 ID の有効期限が切れると、誰も会議に参加できます。 ユーザーがリンクまたは電話で会議に参加しようとすると、会議が利用できなくなったというメッセージが表示されます。 会話、ファイル、ホワイトボード、レコーディング、トランスクリプト、会議に関連するその他のコンテンツは保持され、ユーザーは引き続きアクセスできます。

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>会議ポリシーの設定をオンまたはオフにすると、何が起こりますか?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>会議ポリシーの設定をオンからオフに切り替える

会議ポリシー設定が [オン]に設定されている場合、ポリシーが割り当てられているユーザーは、その種類の会議を開始またはスケジュールし、すべてのユーザーが参加できます。 会議ポリシー設定を [オフ]に切り替えた場合、ポリシーが割り当てられているユーザーは、その種類の新しい会議を開始またはスケジュールできないので、ユーザーが以前にスケジュールした既存の会議の会議への参加リンクと会議 ID の有効期限が切れています。

ユーザーは、他のユーザーが開催した会議に引き続き参加できます。

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>会議ポリシー設定をオフからオンに切り替える

会議ポリシー設定を [オフ]から [**オン**] に切り替える場合、ポリシーが割り当てられているユーザーは、その種類の会議を開始またはスケジュールできます。 ユーザーに対して会議ポリシー設定をオフにしてから再度有効にすると、ユーザーが開催した以前にスケジュールされた会議 (および期限切れ) の会議はすべてアクティブになり、ユーザーは会議参加リンクまたは電話を使用して会議に参加できます。  

## <a name="meeting-expiration-scenarios"></a>会議の有効期限のシナリオ

ここでは、この記事で説明する各会議ポリシー設定で、会議の有効期限がどのように機能するのかについて簡単に説明します。 

|もしこういう場合は... |操作  |会議参加の動作  |
|---------|---------|---------|
|ユーザーが開始した [今すぐ会議] チャネルを期限切れにする  |チャネルで **[今すぐ会う] をオフにします**。|ユーザーが開始した [今すぐ会議] チャネルに参加できるユーザーはいな。         |
|ユーザーがスケジュールしたチャネル会議の有効期限が切れる   |[チャネル会議 **のスケジュール設定を許可する] をオフにします**。         |ユーザーがスケジュールしたチャネル会議には誰も参加できます。 これにより、ユーザーは次の情報に参加する必要がなされます。<ul><li>過去に発生したチャネル会議。</li> <li>将来に予定されている、まだ発生していないチャネル会議。</li><li>定期的なチャネル会議の今後のインスタンス。</li></ul>       |
|ユーザーがスケジュールした非公開の会議の有効期限を切る    |[非公開の **会議のスケジュール設定を許可する] を***オフ* にし、[Outlook アドインを許可 **する] をオフにします**。          |ユーザーがスケジュールした非公開の会議には誰も参加できます。 これにより、ユーザーは次の情報に参加する必要がなされます。 <ul><li>過去に行ったプライベート会議。</li> <li>将来予定されている、まだ行っていない非公開の会議。</li><li>定期的なプライベート会議の今後のインスタンス。</li></ul> ユーザー **がスケジュールしたプライベート会議** を期限切れにするには、[プライベート会議のスケジュールを許可する] と **[Outlook** アドインを許可する] の両方をオフにする必要があります。 一方の設定がオフで、もう一方の設定がオンになっている場合、既存の会議の会議参加リンクと会議の会議の情報はアクティブなままであり、有効期限が切れはされません。      |
|ユーザーが開始したプライベート会議の有効期限が切れる  |プライベート会議 **で [今すぐ会議を許可する] をオフにします**。          |ユーザーが開始したプライベート Meet Now 会議には、誰も参加できます。         |

特定のユーザーが以前にスケジュールまたは開始した会議にユーザーがアクセスする場合は、次の方法を実行できます。

- そのユーザーの会議ポリシー設定を有効にします。
- そのユーザーの会議ポリシー設定をオフにし、ポリシー設定を有効にしている別のユーザーに、期限切れの会議を置き換える新しい会議を作成します。

> [!NOTE]
> 会議が代理人によって送信された場合、他のユーザー (マネージャーなど) の代わりに会議出席依頼を送信するアクセス許可が与えられた場合、会議ポリシーの設定は、アクセス許可を付与したユーザー (マネージャー) に適用されます。

## <a name="related-topics"></a>関連項目

[Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)

[Teams でユーザーにポリシーを割り当てる](assign-policies.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)