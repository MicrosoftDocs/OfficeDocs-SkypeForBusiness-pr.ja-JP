---
title: 管理センターでチーム テンプレートを管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 管理センターでチーム テンプレートを管理する方法について説明します
ms.openlocfilehash: 5370353b38813230ab4329f8a5ad7368efe6c916
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198309"
---
# <a name="manage-team-templates-in-the-admin-center"></a>管理センターでチーム テンプレートを管理する

エンド ユーザーに表示されるチーム テンプレートを管理するには、管理センターでテンプレート ポリシーを作成します。 各テンプレート ポリシー内で、表示または非表示にするテンプレートを指定できます。
ユーザーが指定したチーム テンプレートのサブセットのみを表示できるように、異なるユーザーを異なるテンプレート ポリシーに割り当てます。

テンプレート ポリシーを管理する方法については、この短いビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-templates-policies-and-assign-available-templates"></a>テンプレート ポリシーを作成し、使用可能なテンプレートを割り当てる

1. Teams 管理センターにサインインします。

2. **[Teams** > **テンプレート ポリシー]** に移動します。

3. Choose **Add**.

    ![テンプレート ポリシーが選択され、[追加] が強調表示されています。](media/template-policies-1.png)

1. ポリシーに名前を付け、簡単な説明を追加します。

2. [ **表示可能なテンプレート** ] の一覧で、非表示にするテンプレートを選択し、[非表示] を選択 **します**。

    ![非表示が強調表示されている選択したテンプレート。](media/template-policies-2.png)

    非表示にするテンプレートは、[ **非表示** テンプレート] の一覧で確認できます。

1. 特定のテンプレートを再表示するには、 **非表示のテンプレート** の一覧に移動します。

2. 再表示するテンプレートを選択し、[ **表示**] を選択します。

   ![非表示になっていない選択したテンプレート。](media/template-policies-3.png)

   選択したテンプレートが [ **表示可能なテンプレート** ] の一覧に表示されます。
3. [ **保存**] を選びます。

   新しいテンプレート ポリシーが [ **テンプレート ポリシー** ] の一覧に表示されます。

## <a name="assign-templates-policies-to-users"></a>テンプレート ポリシーをユーザーに割り当てる

テンプレート ポリシーは、個別に、またはバッチ割り当てを使用して大規模にユーザーに直接割り当てることができます。 新しいポリシーがユーザーに有効になるまでに最大 24 時間かかる場合があることに注意してください。

> [!Note]
> 現時点では、セキュリティ グループ内のすべてのユーザーなど、グループ メンバーシップに基づいてテンプレート ポリシーをユーザーに割り当てることはサポートされていません。 この機能は、今後使用できるようになります。

Teams でポリシーを割り当てる方法の概要については、「Teams での [ポリシーの割り当て](policy-assignment-overview.md)」を参照してください。

### <a name="assign-a-templates-policy-to-individual-users"></a>個々のユーザーにテンプレート ポリシーを割り当てる

Teams 管理センターまたは PowerShell を使用して、個々のユーザーまたは一度に少数のユーザーにテンプレート ポリシーを割り当てることができます。 詳細については、「個々の [ユーザーにポリシーを割り当てる](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)」を参照してください。

### <a name="assign-a-templates-policy-to-a-batch-of-users"></a>ユーザーのバッチにテンプレート ポリシーを割り当てる

PowerShell を使用して、一度に多数のユーザー セットにテンプレート ポリシーを割り当てることができます。 これを行うには、 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットと TeamsTemplatePermissionPolicy を として ```PolicyType``` 使用して、割り当てるユーザーとテンプレート ポリシーのバッチを送信します。 次に例を示します。

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName <Any operation name> -PolicyType TeamsTemplatePermissionPolicy -PolicyName <policy name> -Identity <users identity | list of user identities>
```

割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。 その後、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチの割り当ての進捗状況と状態を追跡できます。

詳細については、「 [PowerShell を使用してユーザーのバッチにポリシーを割り当てる](assign-policies-users-and-groups.md#use-powershell-method)」を参照してください。

## <a name="size-limits-for-templates-policies"></a>テンプレート ポリシーのサイズ制限

ポリシーごとに最大 100 個のテンプレートを非表示にすることができます。 指定されたポリシーに既に 100 個のテンプレートが非表示になっている場合、[ **非表示** ] ボタンは無効になります。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Q: 新しいテンプレートが作成された場合、テンプレートはポリシーに含まれますか?**

A: 新しいテンプレートは既定で表示されます。 管理センターの [テンプレート ポリシー] セクションでテンプレートを非表示にすることもできます。

**Q: テンプレートが削除された場合はどうなりますか?**

A: 削除されたテンプレートは、テンプレート ポリシーに存在しなくなります。

**Q: Teams 管理センターのテンプレート ポリシーに複数のユーザーを割り当てることができますか?**

A: はい。

1. Teams 管理センターで、**[ユーザー]** > **[ユーザーの管理]** の順に移動します。
1. ユーザーの一覧で、テンプレート ポリシーに割り当てるユーザーを選択します。
1. [ **設定の編集] を** 選択し、[ **テンプレート ポリシー**] で、割り当てるポリシーを選択します。
1. [ **適用**] を選択します。

詳細については、「個々の [ユーザーにポリシーを割り当てる](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)」を参照してください。

**Q: 特定のポリシー操作方法割り当てられているすべてのユーザーを表示しますか?**

A: Teams 管理センターで次の手順を実行します。

1. [**ユーザー]**[**ユーザーの管理]** >  の順に移動します。
2. [ **フィルター] を** 選択し、テンプレート ポリシーのフィルターを設定し、[ **適用**] を選択します。

    ![選択したテンプレート ポリシーとユーザーの表示。](media/template-policies-5.png)

**Q: PowerShell を使用してテンプレート ポリシーを管理できますか?**

A: いいえ。PowerShell でのテンプレート ポリシーの管理はサポートされていません。 ただし、PowerShell を使用して [、テンプレート ポリシーをユーザーに割り当てることができます](#assign-templates-policies-to-users) 。

**Q: テンプレート ポリシーは EDU に適用されますか?**

A: いいえ。EDU のテンプレート ポリシーはサポートされていません。

## <a name="related-articles"></a>関連記事

- [管理センターでのチーム テンプレートの使用](./get-started-with-teams-templates-in-the-admin-console.md)

- [カスタム チーム テンプレートを作成する](./create-a-team-template.md)

- [既存のチームからテンプレートを作成する](./create-template-from-existing-team.md)

- [既存のチーム テンプレートからチーム テンプレートを作成する](./create-template-from-existing-template.md)

- [Microsoft Teams のユーザーにポリシーを割り当てる - Teams Microsoft Docs Microsoft \|](./policy-assignment-overview.md)

- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
