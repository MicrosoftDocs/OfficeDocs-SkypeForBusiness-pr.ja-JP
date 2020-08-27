---
title: Microsoft Teams で発信者番号ポリシーを管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で発信者番号ポリシーを使用および管理して、組織内の Teams ユーザーの発信者番号を変更またはブロックする方法について説明します。
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255530"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Microsoft Teams で発信者番号ポリシーを管理する

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

管理者は、Microsoft Teams で発信者番号ポリシーを使用して、発信者番号 (発信回線 ID とも呼ばれます) を変更またはブロックできます。 既定では、Teams ユーザーが PSTN 電話に電話をかけると、Teams ユーザーの電話番号が表示され、PSTN 発信者が Teams ユーザーに電話をかけると、PSTN 発信者の電話番号が表示されます。 発信者番号ポリシーを使用すると、組織内の Teams ユーザーの代替電話番号を表示したり、着信番号が表示されないようにブロックしたりできます。

たとえば、ユーザーが電話をかけるときに、ユーザーの電話番号の代わりに組織の代表電話番号が表示されるように発信者番号を変更できます。

発信者番号ポリシーを管理するには、Microsoft Teams 管理センターで **[音声]** > **[発信者番号ポリシー]** の順に移動します。 グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。 カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。

## <a name="create-a-custom-caller-id-policy"></a>カスタム発信者番号ポリシーを作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[音声]** > **[発信者番号ポリシー]** の順に移動します。
2. **[追加]** をクリックします。 <br>
![管理センターの新しい [発信者番号ポリシー] ページのスクリーン ショット](media/caller-id-policies-add-policy.png)
3. ポリシーの名前と説明を入力します。
4. ここで、希望する設定を選びます。

    - **[Block incoming caller ID](着信した発信者番号をブロックする)**: この設定をオンにすると、着信した通話の発信者番号が表示されないようにブロックされます。
    - **発信者番号ポリシーを無効**にする: この設定を有効にすると、ユーザーがポリシーの設定を上書きして、呼び出し先の番号を表示するかどうかを指定することができます。 つまり、発信者番号を表示するかどうかをユーザー自身が選択できます。 詳細については、「 [発信の発信者番号のエンドユーザーによる制御](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)」を参照してください。
    - **発信者**番号認識の代わりに、次のいずれかを選択して、ユーザーに表示される発信者番号を設定します。

        - **[ユーザーの番号]**: ユーザーの番号を表示します。 
        - **[サービス番号]**: サービス電話番号が発信者番号として表示されるように設定できるようになります。
        - **[匿名]**: 発信者番号が [匿名] として表示されます。

    - **発信者番号をこのサービス番号に変更**します。ユーザーの発信者番号を置き換えるサービス番号を選択します。 このオプションは、[発信者番号認識**の代わり**に**サービス番号**] を選択した場合に使用できます。

5. **[保存]** をクリックします。

## <a name="edit-a-caller-id-policy"></a>発信者番号ポリシーを編集する

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。 

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[音声]** > **[発信者番号ポリシー]** の順に移動します。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 目的に合わせて設定を変更したら、**[保存]** をクリックします。

## <a name="assign-a-custom-caller-id-policy-to-users"></a>カスタム発信者番号ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>関連項目

[New-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[チームのユーザーにポリシーを割り当てる](assign-policies.md)
