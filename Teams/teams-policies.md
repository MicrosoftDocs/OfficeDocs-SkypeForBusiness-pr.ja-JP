---
title: Microsoft Teams でチーム ポリシーを管理する
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
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
description: ユーザーがチームやチャネルで実行できる操作を制御する組織のチーム ポリシーの使用方法と管理方法について説明します。
ms.openlocfilehash: 0b4664c36f24a057a7c8237823b7eafaad8ea6ba
ms.sourcegitcommit: 44bd56f67b1ad85ef8c21bb30d5b0d47e5a80339
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49772033"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Microsoft Teams でチーム ポリシーを管理する

管理者は、Microsoft Teams でチーム ポリシーを使用して、チームやチャネルで組織のユーザーが実行できる操作を制御できます。 たとえば、ユーザーにプライベート チャネルの作成を許可するかどうかを設定できます。

チーム ポリシーを管理するには、Microsoft Teams 管理センターで **[Teams]** > **[チーム ポリシー]** の順に移動します。 グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。 カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。

グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。 グローバル ポリシーを編集するか、ポリシーを割り当てると、変更が有効なまで数時間かかる場合があります。

## <a name="create-a-custom-teams-policy"></a>カスタムのチーム ポリシーを作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。

    ![チーム ポリシー設定のスクリーンショット](media/teams-policies.png)
4. ユーザーにプライベート チャネル<a name="createchannels"></a>の作成を許可するかどうかに応じて、プライベート チャネルの作成をオンまたはオフにします。

5. **[保存]** をクリックします。

## <a name="edit-a-teams-policy"></a>チーム ポリシーの編集

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 希望する設定をオンまたはオフにしてから、**[保存]** をクリックします。

## <a name="assign-a-custom-teams-policy-to-users"></a>ユーザーにカスタムのチーム ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>関連トピック

[Teams のプライベート チャネル](private-channels.md)

[ Teams でユーザーにポリシーを割り当てる](assign-policies.md)

[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
