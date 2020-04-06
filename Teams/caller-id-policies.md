---
title: Microsoft Teams で発信者番号ポリシーを管理する
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: ff2f9a02bdf91eb6296dce03e426be673f83495a
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824545"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Microsoft Teams で発信者番号ポリシーを管理する

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

管理者は、Microsoft Teams で発信者番号ポリシーを使用して、発信者番号 (発信回線 ID とも呼ばれます) を変更またはブロックできます。 既定では、Teams ユーザーが PSTN 電話に電話をかけると、Teams ユーザーの電話番号が表示され、PSTN 発信者が Teams ユーザーに電話をかけると、PSTN 発信者の電話番号が表示されます。 発信者番号ポリシーを使用すると、組織内の Teams ユーザーの代替電話番号を表示したり、着信番号が表示されないようにブロックしたりできます。

たとえば、ユーザーが電話をかけるときに、ユーザーの電話番号の代わりに組織の代表電話番号が表示されるように発信者番号を変更できます。

発信者番号ポリシーを管理するには、Microsoft Teams 管理センターで **[音声]** > **[発信者番号ポリシー]** の順に移動します。 グローバル (組織全体の既定) ポリシーを使用することも、カスタム ポリシーを作成してユーザーに割り当てることもできます。 カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。

グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。 ユーザーにカスタム ポリシーが割り当てられると、そのポリシーがユーザーに適用されます。 ユーザーにカスタム ポリシーが割り当てられない場合は、グローバル ポリシーがユーザーに適用されます。

## <a name="create-a-custom-caller-id-policy"></a>カスタム発信者番号ポリシーを作成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[音声]** > **[発信者番号ポリシー]** の順に移動します。
2. **[追加]** をクリックします。
![管理センターの新しい [発信者番号ポリシー] ページのスクリーン ショット](media/caller-id-policies-add-policy.png)
3. ポリシーの名前と説明を入力します。
4. ここで、希望する設定を選びます。

    - **[Block incoming caller ID](着信した発信者番号をブロックする)**: この設定をオンにすると、着信した通話の発信者番号が表示されないようにブロックされます。
    - **[Users can override the caller ID policy](ユーザーに発信者番号ポリシーの上書きを許可する)**: この設定をオンにすると、ユーザーは自分の番号が受信者に表示されるかどうかに関するポリシーの設定を上書きすることができます。 つまり、発信者番号を表示するかどうかをユーザー自身が選択できます。
    - **[Replace caller ID](発信者番号を置換する)**: 次のいずれかを選択して、ユーザーに対して表示される発信者番号を設定します。

        - **[ユーザーの番号]**: ユーザーの番号を表示します。 
        - **[サービス番号]**: サービス電話番号が発信者番号として表示されるように設定できるようになります。
        - **[匿名]**: 発信者番号が [匿名] として表示されます。

    - **[Service number to use to replace the caller ID](発信者番号の代わりに使用するサービス番号)**: ユーザーの発信者番号の代わりに使用するサービス番号を選択します。 このオプションは、**[Replace caller ID](発信者番号を置換する)** で **[サービス番号]** を選択した場合に使用できます。

5. **[保存]** をクリックします。

## <a name="edit-a-caller-id-policy"></a>発信者番号ポリシーを編集する

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。 

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[音声]** > **[発信者番号ポリシー]** の順に移動します。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 目的に合わせて設定を変更したら、**[保存]** をクリックします。

## <a name="assign-a-custom-caller-id-policy-to-users"></a>カスタム発信者番号ポリシーをユーザーに割り当てる

Microsoft Teams 管理センターを使用して、1 つ以上のユーザーまたは Skype for Business PowerShell モジュールにカスタム ポリシーを割り当てることで、セキュリティグループや配布グループなどのユーザーのグループにカスタム ポリシーを割り当てることができます。

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a>カスタム発信者回線 ID ポリシーをユーザーに割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。
3. **[発信者番号ポリシー]** で、割り当てるポリシーを選択し、**[保存]** を選択します。

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a>カスタム発信回線 ID ポリシーを複数のユーザーに一度に割り当てる

一度に複数のユーザーにカスタム発信回線 ID ポリシーを割り当てる方法については、「[一括で Teams のユーザー設定を編集する](edit-user-settings-in-bulk.md)」を参照してください。

または、次の操作も実行できます。

1. **[Microsoft Teams 管理センター]** > **[音声]** > **[発信者番号ポリシー]** の順に移動します。
2. ポリシー名の左側をクリックしてポリシーを選びます。
3. [**ユーザーを管理**] を選択します。
4. [**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。 追加するユーザーごとに、この手順を繰り返します。
5. ユーザーの追加が完了したら、**[保存]** を選択します。

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a>カスタム発信者番号ポリシーをグループ内のユーザーに割り当てる

あらかじめ特定した複数のユーザーにカスタム ポリシーを割り当てることができます。 たとえば、セキュリティ グループのすべてのユーザーにポリシーを割り当てることができます。 これを行うには、Graph 用 Azure Active Directory PowerShell モジュールと Skype for Business PowerShell モジュールに接続します。 PowerShell を使用して Teams を管理する方法の詳細については、「[Teams での PowerShell の概要](teams-powershell-overview.md)」を参照してください。

この例では、「Support Caller ID Policy」という名前のカスタム発信者番号ポリシーを、Contoso サポート グループのすべてのユーザーに割り当てます。  

> [!NOTE]
> 「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。

特定のグループの GroupObjectId を取得します。
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
指定したグループのメンバーを取得します。
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
グループ内のすべてのユーザーを特定の発信者番号ポリシーに割り当てます。 この例では、Support Caller ID Policy を割り当てます。
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。

 ## <a name="related-topics"></a>関連項目

- [New-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

