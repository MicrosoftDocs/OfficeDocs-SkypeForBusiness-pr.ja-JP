---
title: Microsoft Teamsでチャネル ポリシーを管理する
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: 組織内のチーム チャネル ポリシーを使用して管理し、チームとチャネルでユーザーが実行できる操作を制御する方法について説明します。
ms.openlocfilehash: 5acac362485b1004e1db61229c437810fdbcbc6d
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711781"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Microsoft Teamsでチャネル ポリシーを管理する

管理者は、Microsoft Teamsのポリシーを使用して、組織内のユーザーがチームやチャネルで実行できる操作を制御できます。 たとえば、ユーザーがプライベート チャネルまたは共有チャネルの作成を許可するかどうかを設定できます。

チーム ポリシーを管理するには、Microsoft Teams 管理センターで **[Teams]** > **[チーム ポリシー]** の順に移動します。 グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。 カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。

グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。 グローバル ポリシーを編集するか、ポリシーを割り当てた後、変更が有効になるには 24 時間かかる場合があります。

## <a name="channel-policies"></a>チャネル ポリシー

チーム チャネルでは、次のポリシーを使用できます。

|ポリシー|説明|
|:-----|:----------|
|**プライベート チャネルを作成する**|**[オン] の** 場合、チームの所有者とメンバーはプライベート チャネルを作成できます。 (チームの所有者は、メンバーが各チームにプライベート チャネルを作成できるかどうかを制御できます。|
|**共有チャネルを作成する**|**オンの** 場合、チーム所有者は共有チャネルを作成できます。 組織で使用できるTeams アプリは、共有チャネルでも利用できます。|
|**外部ユーザーを共有チャネルに招待する**|**[オン] の** 場合、共有チャネルの所有者とメンバーは、組織間信頼が構成されている組織から外部参加者を招待できます。 組織のTeamsポリシーがこれらのチャネルに適用されます。|
|**外部共有チャネルに参加する**|**[オン] の** 場合、ユーザーは、組織間信頼が構成されている他の組織によって作成された共有チャネルに参加できます。 他の組織のTeams ポリシーがこれらのチャネルに適用されます。|

## <a name="create-a-custom-teams-policy"></a>カスタムのチーム ポリシーを作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。

    ![Teams ポリシー設定のスクリーンショット。](media/teams-policies.png)
4. 希望する設定をオンまたはオフにしてから、**[保存]** をクリックします。

5. **[保存]** をクリックします。

## <a name="edit-a-teams-policy"></a>チーム ポリシーの編集

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 希望する設定をオンまたはオフにしてから、**[保存]** をクリックします。

## <a name="assign-a-custom-teams-policy-to-users"></a>ユーザーにカスタムのチーム ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>関連項目

[Teams 接続済みサイトとチャネル サイトの管理](/SharePoint/teams-connected-sites)

[Teams のプライベート チャネル](private-channels.md)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
