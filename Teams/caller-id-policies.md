---
title: Microsoft Teams で発信者番号ポリシーを管理する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
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
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams で発信者番号ポリシーを使用および管理して、組織内の Teams ユーザーの発信者番号を変更またはブロックする方法について説明します。
ms.openlocfilehash: 4abeccb7a536885707ec43874d00f2a05a14551d
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414705"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Microsoft Teams で発信者番号ポリシーを管理する

既定では、Teams ユーザーが PSTN 電話を呼び出すと、Teams ユーザーの電話番号が表示されます。 同様に、PSTN 発信者が Teams ユーザーに通話を行うと、PSTN 発信者の電話番号が表示されます。

管理者は、発信者 ID ポリシーを使用して、発信者 ID (呼び出し元の行 ID とも呼ばれます) を変更またはブロックできます。 発信者 ID ポリシーを使用すると、組織内の Teams ユーザーの代替電話番号を表示したり、送信電話番号をブロックしたり、着信番号の表示をブロックしたり、通話者名 (CNAM) を設定したりできます。 たとえば、ユーザーが通話を行うときに、発信者番号を変更して、ユーザーの電話番号ではなく、組織の主要な電話番号と会社名を表示できます。

発信者番号ポリシーを管理するには、Microsoft Teams 管理センターで **[音声]** > **[発信者番号ポリシー]** の順に移動します。 グローバル (組織全体の既定) ポリシーを使用ことも、カスタム ポリシーを作成して割り当てることもできます。 カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。

## <a name="create-a-custom-caller-id-policy"></a>カスタム発信者番号ポリシーを作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[音声]** > **[発信者番号ポリシー]** の順に移動します。
2. **[追加]** をクリックします。 <br>
![管理センターの新しい発信者 ID ポリシー ページのスクリーンショット。](media/caller-id-policies-add-policy.png)
3. ポリシーの名前と説明を入力します。
4. ここで、希望する設定を選びます。

    - **[着信した発信者番号をブロックする]**: この設定をオンにすると、着信した通話の発信者番号が表示されないようにブロックされます。
    - **[発信者番号ポリシーの上書き]**: この設定をオンにすると、ユーザーは自分の番号が受信者に表示されるかどうかに関するポリシーの設定を上書きすることができます。 つまり、発信者番号を表示するかどうかをユーザー自身が選択できます。 詳細については、「[発信者番号のエンド ユーザー制御](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)」を参照してください。
    - **[発信者番号を置換する]**: 次のいずれかを選択して、ユーザーに対して表示される発信者番号を設定します。

        - **[ユーザーの番号]**: ユーザーの番号を表示します。 
        - **[サービス番号]**: サービス電話番号が発信者番号として表示されるように設定できるようになります。
        - **[匿名]**: 発信者番号が [匿名] として表示されます。

    - **[発信者番号をこのサービス番号に置換する]**: ユーザーの発信者番号の代わりに使用するサービス番号を選択します。 このオプションは、**[発信者番号を置換する]** で **[サービス番号]** を選択した場合に使用できます。

5. **[保存]** をクリックします。

## <a name="edit-a-caller-id-policy"></a>発信者番号ポリシーを編集する

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。 

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[音声]** > **[発信者番号ポリシー]** の順に移動します。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 目的に合わせて設定を変更したら、**[保存]** をクリックします。

## <a name="assign-a-custom-caller-id-policy-to-users"></a>カスタム発信者番号ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>関連項目

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)
