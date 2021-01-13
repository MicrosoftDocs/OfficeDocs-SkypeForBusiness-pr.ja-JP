---
title: Microsoft Teams でフィードバック ポリシーを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: msedliak
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
description: フィードバック ポリシーを使用して、組織内の Teams ユーザーが Teams に関するフィードバックを Microsoft に送信できるかどうかを制御する方法について説明します。
ms.openlocfilehash: e2415204650ce47f875e432f062fd4a5e0438cd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804697"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Microsoft Teams でフィードバック ポリシーを管理する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

組織内のユーザーは、Teams に関するフィードバックを Microsoft に送信できます。Teams デスクトップおよび Web クライアント内から直接、Microsoft の取り組みについてお知らせします。 Teams のエクスペリエンスは継続的に改善され、このフィードバックを使用して Teams の改善に努めしています。

> [!NOTE]
> フィードバック ポリシーは、GCC、GCC High、DOD 展開では利用できません。

**フィードバックを送信する機能**

ユーザーは、Teams でフィードバックを送信する方法にアクセスして、Teams に関するコメントや提案  >  **を** 送信できます。 フィードバックを送信したデータは、Microsoft 365 または Office 365 契約に基く "サポート データ" と見なされます。その他の方法で "顧客データ" または "個人データ" と見なされる情報を含む。

![Teams の [フィードバックの送信] オプションのスクリーンショット](media/manage-feedback-policies-in-teams-give-feedback.png)

**アンケート**

また、ユーザーは Teams でのエクスペリエンスを評価し、評価に関する詳細を送信できます。 このポップアップ アンケートは、Teams でユーザーに対してときおり表示されます。 ユーザーが [通知 **にフィードバックを** 送信する] をクリックすると、アンケートが表示され、完了します。

![Teams のアンケートの通知とフォームのスクリーンショット](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>ユーザーが Teams に関するフィードバックを Microsoft に送信できるかどうかを設定する

管理者は、組織内のユーザーがフィードバックを送信して Teams に関するフィードバックを Microsoftに送信できるかどうか、およびユーザーがアンケートを受け取ったかどうかを制御できます。 既定では、組織内のすべてのユーザーにグローバル (組織全体の既定) ポリシーが自動的に割り当て、ポリシーで [フィードバックの送信] 機能とアンケートが有効になります。 ただし、教師に対して機能が有効になり、学生に対して無効になっている Teams for Education は例外です。

グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。 グローバル ポリシーを編集するか、カスタム ポリシーを割り当てると、変更が有効なまで数時間かかる場合があります。

たとえば、トレーニングの新入社員を除き、組織内のすべてのユーザーがフィードバックを送信し、アンケートを受け取る場合を許可するとします。 このシナリオでは、両方の機能をオフにし、新入社員に割り当てるカスタム ポリシーを作成します。 組織内の他のすべてのユーザーは、機能が有効になっているグローバル ポリシーを取得します。  

PowerShell を使用してフィードバック ポリシーを管理します。 カスタム ポリシーと **Grant-CsTeamsFeedbackPolicy** コマンドレットを作成して、セキュリティ グループや配布グループなどの 1 つ以上のユーザーまたはユーザー グループに割り当てるには **、New-CsTeamsFeedbackPolicy** コマンドレットを使用します。このコマンドレットを使用します。 *[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*

機能をオフにし、有効にする場合は、次のパラメーターを設定します。

 - **フィードバックの送信**: ポリシーが割り当てられているユーザーがフィードバックを提供するために **、userInitiatedMode** パラメーターを有効に設定します。 パラメーターを無効に **設定すると** 、機能が無効になり、ポリシーが割り当てられているユーザーにはフィードバックを送信するオプションはありません。
 - **アンケート**: **receiveSurveysMode** パラメーターを有効に設定して、ポリシーが割り当てられているユーザーがアンケートを受け取るのを許可します。 ユーザーにアンケートを受け取ってオプトアウトを許可するには、パラメーターを **enabledUserOverride に設定します**。 Teams では、ユーザーは [**設定のプライバシー**] に移動し、アンケートに参加  >  するかどうかを選択できます。 パラメーターを無効に **設定すると** 、機能が無効になり、ポリシーが割り当てられているユーザーはアンケートを受け取らできなくなります。

## <a name="create-a-custom-feedback-policy"></a>カスタム フィードバック ポリシーを作成する

この例では、新入社員フィードバック ポリシーと呼ばれるフィードバック ポリシーを作成し、フィードバックとアンケートを使用してフィードバックを送信する **機能をオフ** にします。

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>ユーザーにカスタム フィードバック ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

この例では、user1 という名前のユーザーに新入社員フィードバック ポリシーというカスタム ポリシーを割り当てします。

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>関連トピック

- [Teams PowerShell の概要](teams-powershell-overview.md)
- [ Teams でユーザーにポリシーを割り当てる](assign-policies.md)