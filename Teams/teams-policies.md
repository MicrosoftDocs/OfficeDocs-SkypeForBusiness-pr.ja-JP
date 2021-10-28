---
title: チャネル ポリシーを管理Microsoft Teams
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
description: 組織内のチーム チャネル ポリシーを使用して管理し、ユーザーがチームやチャネルで実行できる操作を制御する方法について説明します。
ms.openlocfilehash: 787978d6863a66b39c75f3f2c7315fe1495730c3
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605613"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>チャネル ポリシーを管理Microsoft Teams

管理者は、Microsoft Teams でチーム ポリシーを使用して、チームやチャネルで組織のユーザーが実行できる操作を制御できます。 たとえば、ユーザーがプライベート チャネルを作成できるかどうかを設定できます。

チーム ポリシーを管理するには、Microsoft Teams 管理センターで **[Teams]** > **[チーム ポリシー]** の順に移動します。 グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。 カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。

グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。 グローバル ポリシーを編集するか、ポリシーを割り当てると、変更が有効なまで数時間かかる場合があります。

## <a name="create-a-custom-teams-policy"></a>カスタムのチーム ポリシーを作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。

    ![Teams のポリシー設定のスクリーンショット。](media/teams-policies.png)
4. ユーザーにプライベート チャネルの **作成**<a name="createchannels"></a>を許可するかどうかに応じて、[プライベート チャネルの作成] をオンまたはオフにします。

5. **[保存]** をクリックします。

## <a name="edit-a-teams-policy"></a>チーム ポリシーの編集

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 希望する設定をオンまたはオフにしてから、**[保存]** をクリックします。

## <a name="assign-a-custom-teams-policy-to-users"></a>ユーザーにカスタムのチーム ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>関連トピック

[Teams 接続済みサイトとチャネル サイトの管理](/SharePoint/teams-connected-sites)

[Teams のプライベート チャネル](private-channels.md)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
