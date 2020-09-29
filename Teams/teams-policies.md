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
description: ユーザーがチームやチャネルで実行できる操作を制御する組織のチーム ポリシーの使用方法と管理方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: ad7dadc60b1fb53a518ec5cab340739a89f6b044
ms.sourcegitcommit: 6f4928e9e7e67fe65320131ae9e7348b948d86ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "48297375"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Microsoft Teams でチーム ポリシーを管理する

管理者は、Microsoft Teams でチーム ポリシーを使用して、チームやチャネルで組織のユーザーが実行できる操作を制御できます。 たとえば、プライベートチャネルを作成することをユーザーに許可するかどうかを設定できます。

チーム ポリシーを管理するには、Microsoft Teams 管理センターで **[Teams]** > **[チーム ポリシー]** の順に移動します。 グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。 カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。

グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。 グローバルポリシーを編集するか、ポリシーを割り当てると、変更が有効になるまでに数時間かかることがあります。

## <a name="create-a-custom-teams-policy"></a>カスタムのチーム ポリシーを作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。

    ![チーム ポリシー設定のスクリーンショット](media/teams-policies.png)
4. プライベートチャネルの作成を許可するかどう<a name="createchannels"> </a>かに応じて、**プライベートチャネルの作成**をオンまたはオフにします。

5. **[保存]** をクリックします。

## <a name="edit-a-teams-policy"></a>チーム ポリシーの編集

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams]** > **[チーム ポリシー]** の順に移動します。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 希望する設定をオンまたはオフにしてから、**[保存]** をクリックします。

## <a name="assign-a-custom-teams-policy-to-users"></a>ユーザーにカスタムのチーム ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>関連項目

[Teams のプライベート チャネル](private-channels.md)

[チームのユーザーにポリシーを割り当てる](assign-policies.md)
