---
title: Microsoft Teams でフィードバック ポリシーを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: heprecel
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 組織内の Teams ユーザーが Teams に関するフィードバックを Microsoft に送信できるかどうかを制御するフィードバック ポリシーの使用方法について説明します。
ms.openlocfilehash: 66f14467e66456f244664a8273e0ff962297c05f
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656723"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Microsoft Teams でフィードバック ポリシーを管理する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

組織内のユーザーは、Teams デスクトップおよび Web クライアントから直接、Teams に関するフィードバックを Microsoft に送信できます。 Microsoft は、Teams エクスペリエンスを継続的に向上しており、このフィードバックを使用して Teams を改善しています。

> [!NOTE]
> フィードバック ポリシーは、GCC、GCC High、DOD の展開では使用できません。

**[フィードバックの送信] 機能**

ユーザーは、Teams で **[ヘルプ]** > **[フィードバックの送信]** の順に移動し、Teams に関するコメントや提案を送信できます。 **[フィードバックの送信]** を通じて送信されたデータは、Microsoft 365 または Office 365 契約の「サポート データ」とみなされます。これには、「顧客データ」または「個人データ」と見なされる情報も含まれます。

![Teams の [フィードバックの送信] のスクリーンショット](media/manage-feedback-policies-in-teams-give-feedback.png)

**アンケート**

ユーザーはまた、Teams でのエクスペリエンスを評価し、評価に関する詳細を送信することもできます。 このポップアップ アンケートは、[Teams] に随時表示されます。 ユーザーが通知で **[フィードバックの** 提供] を選択すると、アンケートが表示され、完了します。

![アンケートの通知とフォームのTeams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>ユーザーが Teams に関するフィードバックを Microsoft に送信できるかどうかを設定する

管理者は、組織内のユーザーが **[フィードバックの送信]** で Microsoft に Teams に関するフィードバックを送信できるかどうか、およびアンケートを受信できるかどうかを制御できます。 既定では、組織内のすべてのユーザーにグローバル (組織全体の既定) ポリシーが自動的に割り当て、ポリシーで [フィードバックの提供] 機能とアンケートが有効になります。 例外は、Teams for Education で、この機能は教師に対しては有効になっていますが、生徒に対しては無効になっています。

グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。 グローバル ポリシーを編集するか、カスタム ポリシーを割り当てた後、変更が反映されるまでに数時間かかる場合があります。

たとえば、組織内のすべてのユーザーが **[フィードバックの送信]** でフィードバックを送信し、トレーニング中の新入社員を除いてアンケートを受信できるようにしたいとします。 このシナリオでは、両方の機能をオフにして新入社員に割り当てるカスタム ポリシーを作成します。 組織内の他のすべてのユーザーは、機能をオンにした状態でグローバル ポリシーを取得します。  

フィードバック ポリシーは、PowerShell を使用して管理します。 **New-CsTeamsFeedbackPolicy** コマンドレット (*[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* こちら) を使用して、カスタム ポリシーを作成します。 セキュリティ グループや配布グループなど、1 つ以上のユーザーまたはユーザー グループに割り当てるには **、Grant-CsTeamsFeedbackPolicy** コマンドレットを使用します。 **Set-CsTeamsFeedbackPolicy を使用して、特定** のフラグを設定します。

機能をオフまたはオンにするには、次のパラメーターを設定します。

 - **フィードバックの送信**: **userInitiatedMode** パラメーターを **[有効]** に設定して、ポリシーが割り当てられているユーザーがフィードバックを送信できるようにします。 パラメーターを **[無効]** に設定すると、機能がオフになり、ポリシーが割り当てられているユーザーにはフィードバックを送信するオプションが表示されません。
 - **アンケート**: **receiveSurveysMode** パラメーターを **[有効]** に設定して、ポリシーが割り当てられているユーザーがアンケートを受信できるようにします。 ユーザーがアンケートを受信して受け取らないことができるようにするには、パラメーターを **enabledUserOverride** に設定します。 Teams では、**[設定]** > **[プライバシー]** の順に移動し、アンケートに参加するかどうかを選択できます。 パラメーターを **[無効]** に設定すると、機能がオフになり、ポリシーが割り当てられているユーザーはアンケートを受信できません。
 - **Email**: **AllowEmailCollection フラグを使用して、** 電子メール フィールドを追加します。

## <a name="create-a-custom-feedback-policy"></a>カスタム フィードバック ポリシーを作成する

この例では、[新入社員向けフィードバック ポリシー] というフィードバック ポリシーを作成し、**[フィードバックの送信]** およびアンケートでフィードバックを送信する機能をオフにします。

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>ユーザーにカスタムのフィードバック ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

この例では、user1 という名前のユーザーに [新入社員向けフィードバック ポリシー] という名前のカスタム ポリシーを割り当てます。

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>関連トピック

- [Teams PowerShell の概要](teams-powershell-overview.md)
- [ Teams でユーザーにポリシーを割り当てる](assign-policies.md)
