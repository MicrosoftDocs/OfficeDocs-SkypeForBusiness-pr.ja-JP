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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: フィードバックポリシーを使用して、組織内の Teams ユーザーがチームに関するフィードバックを Microsoft に送信できるかどうかを制御する方法について説明します。
ms.openlocfilehash: 0bece4515825a0d7ddf7e547f1607fbd6cf205cc
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433040"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Microsoft Teams でフィードバックポリシーを管理する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

組織内のユーザーは、teams に関するフィードバックを Microsoft に送信することができます。これは、チームのデスクトップと web クライアントの中から直接行っていることです。 チームのエクスペリエンスを継続的に改善しており、このフィードバックを使用してチームの改善に取り組んでいます。

> [!NOTE]
> フィードバックポリシーは、GCC、GCC 高、または DOD の展開では利用できません。

**フィードバックの提供機能**

ユーザーは、チームでフィードバックを送信する**ために、** チームに関するコメントや提案をお送りし  >  **Give feedback**ます。 **フィードバック**を送信して送信されるデータは、Microsoft 365 または Office 365 契約の下では、"顧客データ" または "個人データ" と見なされる情報を含む "サポートデータ" と見なされます。

![Teams の [フィードバックの提供] オプションのスクリーンショット](media/manage-feedback-policies-in-teams-give-feedback.png)

**調査**

また、ユーザーはチームとのエクスペリエンスを評価し、その評価についての詳細を送信することもできます。 このポップアップアンケートは、チームのユーザーに対して表示されます。 ユーザーが通知の [ **フィードバック** の送信] をクリックすると、アンケートが表示されます。

![Teams でのアンケート通知とフォームのスクリーンショット](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>ユーザーがチームに関するフィードバックを Microsoft に送信できるようにするかどうかを設定する

管理者として、組織内のユーザーが **フィードバック** を送信し、アンケートを受けるかどうかを制御できます。 既定では、組織内のすべてのユーザーにグローバル (組織全体の既定) ポリシーが自動的に割り当てられ、ポリシーで **フィードバックの提供** 機能とアンケートが有効になります。 この例外は、学生に対して機能が有効になっており、学生に対して無効になっている、教育機関向けの Teams です。

グローバル ポリシーを編集するか、カスタム ポリシーを作成して割り当てることもできます。 グローバルポリシーを編集するか、カスタムポリシーを割り当てると、変更が有効になるまでに数時間かかることがあります。

たとえば、組織内のすべてのユーザーが **フィードバック** を送信してフィードバックを受け取り、トレーニングの新入団体以外のアンケートを受けることができるようにします。 このシナリオでは、ユーザー設定のポリシーを作成して、両方の機能を無効にし、新しい採用者に割り当てることができます。 組織内の他のすべてのユーザーは、この機能を有効にしたグローバルポリシーを取得します。  

フィードバックポリシーは、PowerShell を使用して管理します。 *[この](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* コマンド**レットを使用して**、カスタムポリシーを作成します。これは、1人以上のユーザーまたはユーザーのグループ (セキュリティグループ、配布グループなど) に割り当てるために、ユーザー設定のポリシーと**Grant-csteamsフィードバックポリシー**コマンドレットを作成するために使用します。

機能を無効にして有効にするには、次のパラメーターを設定します。

 - **フィードバック**を送信: ポリシーを割り当てられたユーザーがフィードバックを提供できるように、 **Userinitiatedmode** パラメーターを **enabled** に設定します。 パラメーターを [ **無効** ] に設定すると、この機能は無効になり、ポリシーを割り当てられたユーザーにはフィードバックを送信するオプションが表示されなくなります。
 - **アンケート**: ポリシーを割り当てられたユーザーがアンケートを受けることができるように、 **receiveSurveysMode** パラメーターを **enabled** に設定します。 ユーザーにアンケートを受け取り、オプトインすることを許可するには、パラメーターを **Enableduseroverride**に設定します。 Teams では、ユーザーは [**設定**のプライバシー] に移動し  >  **Privacy**て、アンケートに参加するかどうかを選ぶことができます。 パラメーターを [ **無効** ] に設定すると、この機能は無効になり、ポリシーを割り当てられたユーザーはアンケートを受けることができなくなります。

## <a name="create-a-custom-feedback-policy"></a>ユーザー設定のフィードバックポリシーを作成する

この例では、新入社員フィードバックポリシーというフィードバックポリシーを作成し **、フィードバックとアンケートを通じて** フィードバックを提供する機能を無効にします。

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>ユーザーにカスタムフィードバックポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

この例では、新入社員フィードバックポリシーという名前のカスタムポリシーを user1 という名前のユーザーに割り当てています。

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>関連トピック

- [Teams PowerShell の概要](teams-powershell-overview.md)
- [チームのユーザーにポリシーを割り当てる](assign-policies.md)