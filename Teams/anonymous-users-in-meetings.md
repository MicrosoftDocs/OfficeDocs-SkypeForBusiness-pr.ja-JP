---
title: Teams 会議への匿名参加者アクセスを管理する (IT 管理者)
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: IT 担当者向け - Microsoft Teams での匿名会議参加のしくみについて説明します。
ms.openlocfilehash: a4f1833059febf2f8481cba9f1b3716519613e89
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983735"
---
# <a name="manage-anonymous-participant-access-to-teams-meetings-it-admins"></a>Teams 会議への匿名参加者アクセスを管理する (IT 管理者)

組織によってホストされている会議の匿名の参加者は、ID を確認できないユーザーです。 これには、次のものが含まれます。

- 職場または学校アカウントを使用して Teams にログインしていないPeople 
- 信頼されていない組織 ([外部アクセス](manage-external-access.md)で構成されている) および信頼しているが、組織を信頼していない組織からのPeople。

匿名会議参加は、組織レベルの設定とユーザー レベルのポリシーによって制御されます。 匿名会議参加を機能させるには:
- **匿名ユーザーが会議 Teams 会議に参加できる** 設定 (組織レベル) をオンにする必要があります。
- 会議の開催者には、Teams 会議ポリシーが割り当てられている必要があります。ここで、[ **匿名のユーザーが会議に参加できるようにする** ] コントロールがオンになっています。

匿名会議への参加は、組織と既定のグローバル会議ポリシーで既定でオンになっています。 組織レベルの設定をオンにしたまま、会議ポリシーを使用して、さまざまなユーザー (会議開催者) の匿名会議参加をオンまたはオフにすることをお勧めします。

匿名会議参加が有効になっている場合、ロビー ポリシーは匿名の参加者が会議に参加する方法に影響します。 詳細については、「 [Microsoft Teams で会議ロビーをバイパスできるユーザーを制御する](who-can-bypass-meeting-lobby.md)」を参照してください。

#### <a name="meetings-with-trusted-organizations"></a>信頼できる組織との会議

外部会議とチャット用に信頼できる組織を設定すると、外部アクセス設定が両方の組織に対して正しく構成されていない場合、それらの組織の会議出席者は匿名と見なされることがあります。 詳細については、 [外部会議とチャットに関する信頼された組織に関するページを](manage-external-access.md)参照してください。

## <a name="manage-anonymous-meeting-join-for-the-organization"></a>組織の匿名会議参加を管理する

組織内のすべてのユーザーが匿名参加者を許可する会議を作成するには、組織レベルの匿名会議参加設定を有効にする必要があります。

> [!Important]
> **匿名の参加者は、今後、組織全体で会議に参加できる** 設定が削除されます。 この設定 **を [オン] のままに** し **、[匿名のユーザーが会議** ユーザー レベルの会議に参加できるようにする] ポリシー コントロールを使用して、代わりに匿名会議への参加を許可または禁止することをお勧めします。

組織の匿名会議参加を構成するには
1. [Teams 管理センター](https://admin.teams.microsoft.com)に移動します。

1. 左側のナビゲーションで、[**会議**] > [**会議設定**] に移動します。

1. [ **参加者]** で、[ **匿名の参加者が会議に参加できる** ] を **[オン** (推奨)] または **[オフ]** に設定します。

    ![管理センターでの会議の参加者設定のスクリーンショット。](media/meeting-settings-participants.png "Microsoft Teams 管理センターでの Teams 会議の参加者設定のスクリーンショット")

1. **[保存]** を選択します。

## <a name="manage-which-meeting-organizers-can-allow-anonymous-meeting-join"></a>匿名会議への参加を許可できる会議の開催者を管理する

匿名の参加者を含む会議をホストできるユーザーまたはグループを制御できます。 これを行うには、匿名の参加者と会議を開催する必要がある各会議開催者に匿名会議参加が有効になっている会議ポリシーを割り当てます。

特定の会議開催者の匿名会議参加を構成するには
1. [Teams 管理センター](https://admin.teams.microsoft.com)に移動します。

1. 左側のナビゲーションで、[**会議会議ポリシー]** >  に移動 **します**。

1. 変更するポリシーを選択します。

1. [ **匿名のユーザーが会議に参加できるようにする** ] を **[オン]** に設定します。

1. **[保存]** を選択します。

会議ポリシーの変更が有効になるまでに最大 24 時間かかる場合があります。

## <a name="configure-anonymous-meeting-join-using-powershell"></a>PowerShell を使用して匿名会議参加を構成する

匿名の参加者が会議に参加できるかどうかを制御する方法は、次のとおりです。

- `-DisableAnonymousJoin`組織レベルの設定を構成するための [Set-CsTeamsMeetingConfiguration](/powershell/module/skype/set-csteamsmeetingconfiguration) のパラメーター。 (この設定は False のままにし、Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting を使用して、ユーザーまたはグループ レベルで匿名会議参加を制御することをお勧めします)。
- `-AllowAnonymousUsersToJoinMeeting`ユーザー レベルの会議ポリシーを構成するための [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) のパラメーター

匿名の参加者が会議に参加できるようにするには、次の値を設定して匿名会議参加を許可するように両方を構成する必要があります。

- `Set-CsTeamsMeetingConfiguration -DisableAnonymousJoin`**を $false** に設定する
- `Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting` 関連する会議開催者の **$true** に設定する

## <a name="block-anonymous-meeting-join-for-specific-client-types"></a>特定のクライアントの種類に対して匿名会議参加をブロックする

匿名の参加者が会議に参加できる場合は、Teams クライアントまたは [Azure Communication Services](/azure/communication-services/) を使用して構築されたカスタム クライアントを使用できます。 

管理者は、[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy#-blockedanonymousjoinclienttypes) の パラメーターを`-BlockedAnonymousJoinClientTypes`使用して、これらのクライアントの種類のいずれかをブロックできます。

## <a name="anonymous-participants-meeting-experience"></a>匿名の参加者の会議エクスペリエンス

匿名の参加者には、他の会議参加者と同じ機能はありません。 たとえば、匿名の参加者は次のようになります。

- 会議の前後に会議チャットにアクセスできない
- プロファイル カードにアクセスできない (Microsoft 365 のプロファイル カード - Microsoft サポート)

### <a name="how-anonymous-participants-interact-with-apps-in-meetings"></a>匿名の参加者が会議でアプリと対話する方法

既定では、匿名の参加者が会議でアプリと対話できるようにする設定が有効になっています。

匿名会議参加者のアプリ アクセスを構成するには

1. [Teams 管理センター](https://admin.teams.microsoft.com)に移動します。

1. 左側のナビゲーションで、[**会議**] > [**会議設定**] に移動します。

1. [**参加者]** で、[**匿名の参加者が会議でアプリと対話できる**] を [オン] または **[オフ****] に** 設定します。

を使用 `Set-CsTeamsMeetingConfiguration -DisableAppInteractionForAnonymousUsers`して、PowerShell でこれを制御することもできます。

匿名の参加者は、グローバル (組織全体の既定) Teams アプリのアクセス許可ポリシーを継承します。 匿名の参加者は、そのポリシーでアプリが有効になっていて、**匿名の参加者が会議でアプリと対話できる限り、Teams 会議でアプリと対話できます****。**

匿名の参加者は、会議で既に利用できるアプリとのみやり取りでき、これらのアプリの取得および/または管理ができないことに注意してください。

## <a name="related-topics"></a>関連項目

[Teams アカウントを使用せずに会議に参加する](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[Microsoft Teams 管理センターを使用して組織全体のポリシーを構成する](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[外部参加者は"Teams にサインインして参加するか、会議の開催者に連絡する" を受け取ります](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)

[Teams でポリシーを割り当てる - 作業を開始する](policy-assignment-overview.md)