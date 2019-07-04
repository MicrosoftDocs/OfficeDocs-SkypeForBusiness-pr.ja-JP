---
title: Microsoft Teams でフィードバックポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: フィードバックポリシーを使用して、組織内の Teams ユーザーがチームに関するフィードバックを Microsoft に送信できるかどうかを制御する方法について説明します。
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "35540954"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Microsoft Teams でフィードバックポリシーを管理する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

ユーザーは、チームクライアントに**** > **フィードバック**を送信していただくことで、チームに関するコメントや提案を Microsoft に送信できます。 チームのエクスペリエンスを継続的に改善しており、このフィードバックを使用してチームの改善に取り組んでいます。

![Teams の [フィードバックの提供] オプションのスクリーンショット](media/manage-feedback-policies-in-teams-give-feedback.png)

**フィードバック**を送信して送信されるデータは、"顧客データ" または "個人データ" と見なされる情報など、Office 365 契約の下で "サポートデータ" と見なされます。

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>ユーザーがチームに関するフィードバックを Microsoft に送信できるようにするかどうかを設定する

管理者は、組織内のユーザーがチームに関するフィードバックを Microsoft に送信できるかどうかを制御できます。 既定では、組織内のすべてのユーザーにグローバル (組織全体の既定) ポリシーが自動的に割り当てられ、その機能はポリシーで有効になります。 例外とは、教育機関向けの Teams であり、学生のためにこの機能が有効になっており、無効になっています。

グローバルポリシーを編集するか、カスタムポリシーを作成して割り当てることができます。 ユーザーにカスタムポリシーが割り当てられている場合は、そのポリシーがユーザーに適用されます。 ユーザーにカスタムポリシーが割り当てられていない場合は、グローバルポリシーがユーザーに適用されます。 グローバルポリシーを編集するか、ポリシーを割り当てると、変更が有効になるまで最大24時間かかることがあります。

たとえば、組織内のすべてのユーザーが、トレーニングの新入業者を除き、フィードバックを送信することを許可する必要があるとします。 このシナリオでは、ユーザー設定のポリシーを作成して、この機能を無効にして新しい採用者に割り当てることができます。 組織内の他のすべてのユーザーは、この機能が有効になっているグローバルポリシーを取得します。  

**新しい-Csteamsbackpolicy**コマンドレットを使用して、カスタムポリシーを作成し、それを1人以上のユーザーまたはユーザーのグループ (セキュリティグループ、配布グループなど) に割り当てるために、**許可-Csteamsフィードバックポリシー**コマンドレットを使用します。 

ポリシーを割り当てられたユーザーがフィードバックを送信できるようにするには、 **Userinitiatedmode**パラメーターを**enabled**に設定します。 パラメーターを [**無効**] に設定すると、この機能は無効になり、ポリシーを割り当てられたユーザーにはフィードバックを送信するオプションが表示されなくなります。

## <a name="create-a-custom-feedback-policy"></a>ユーザー設定のフィードバックポリシーを作成する

この例では、新入社員フィードバックポリシーというフィードバックポリシーを作成し、フィードバックを提供する機能を無効にします。

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a>ユーザー設定のフィードバックポリシーを割り当てる

### <a name="assign-a-custom-feedback-policy-to-a-user"></a>ユーザーにカスタムフィードバックポリシーを割り当てる

この例では、新入社員フィードバックポリシーという名前のカスタムポリシーを user1 という名前のユーザーに割り当てています。

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a>ユーザー設定のフィードバックポリシーをグループ内のユーザーに割り当てる

ユーザー設定のフィードバックポリシーは、既に指定されている複数のユーザーに割り当てることができます。 たとえば、セキュリティグループ内のすべてのユーザーにポリシーを割り当てることができます。

この例では、新入社員フィードバックポリシーというカスタムフィードバックポリシーを、Contoso の新入社員グループのすべてのユーザーに割り当てます。  

特定のグループの GroupObjectId を取得します。
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
指定したグループのメンバーを取得します。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
グループ内のすべてのユーザーを特定のフィードバックポリシーに割り当てます。 この例では、新入社員フィードバックポリシーが追加されています。
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。

## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)