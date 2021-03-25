---
title: Microsoft Teams で緊急通話ポリシーを管理する
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で緊急通話ポリシーを使用して管理し、組織内の Teams ユーザーが緊急通話を行った場合の対応を定義する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 34f6e901049dd080ee070e7858f24b70535ee189
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120568"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Microsoft Teams で緊急通話ポリシーを管理する

組織で通話プラン[](set-up-calling-plans.md)または展開された電話システム[](direct-routing-landing-page.md)ダイレクト ルーティングを使用している場合は、Microsoft Teams の緊急通話ポリシーを使用して、組織内の Teams ユーザーが緊急通話を行った場合の処理を定義できます。 通知するユーザーと、ポリシーが割り当てられているユーザーが緊急サービスを呼び出したときに通知する方法を設定できます。 たとえば、ポリシー設定を構成して、組織のセキュリティ デスクに自動的に通知し、緊急通話を聞い与えます。  

緊急通話ポリシーを管理するには、Microsoft Teams 管理センターで音声緊急ポリシーに移動するか  >  、Windows PowerShell。 ポリシーは、ユーザーとネットワーク サイトに [割り当てることができます](cloud-voice-network-settings.md)。

ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。 カスタム ポリシーを作成して割り当てない限り、ユーザーは自動的にグローバル ポリシーを取得します。 グローバル ポリシーの設定は編集できますが、名前の変更や削除はできないので、ご安心ください。 ネットワーク サイトの場合は、カスタム ポリシーを作成して割り当てる必要があります。

ネットワーク サイトとユーザーに緊急通話ポリシーを割り当て、そのユーザーがネットワーク サイトにある場合、ネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーを上書きします。

## <a name="create-a-custom-emergency-calling-policy"></a>カスタム緊急通話ポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[音声緊急ポリシー] に移動し、[通話ポリシー] タブ  >  **をクリック** します。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。
4. 緊急通話が行われたときに組織内のユーザー (通常はセキュリティ デスク) に通知する方法を設定します。 これを行うには、[通知モード **] で**、次のいずれかを選択します。
    - **通知のみ送信**: Teams のチャット メッセージは、指定したユーザーとグループに送信されます。
    - **ミュート** 状態で電話会議を行い、ミュートを解除できない : Teams のチャット メッセージは、指定したユーザーとグループに送信され、発信者と PSAP オペレーターの間の会話を聞く (参加できません) できます。
    - **ミュート** で電話会議を行ったが、ミュートを解除できる : Teams のチャット メッセージは、指定したユーザーとグループに送信され、ミュートを解除して発信者と PSAP オペレーター間の会話に参加できます。
5.  いずれかの会議をミュート通知モードで選択した場合は、[緊急通話の通知をダイヤルする番号] ボックスに、ユーザーまたはグループの PSTN 電話番号を入力して、緊急通話を発信して参加することができます。 たとえば、組織のセキュリティ デスクの番号を入力します。緊急通話が行われたときに通話を受け取り、その後、通話を聞き取りできます。 モードがミュートで電話会議に設定されているが、ミュートを解除できる場合でも、PSTN 電話を **ミュート解除することはできません**。
6. 組織のセキュリティ デスクなどの 1 つ以上のユーザーまたはグループを検索して選択し、緊急通話が行われたときに通知します。  通知は、ユーザー、配布グループ、セキュリティ グループのメール アドレスに送信できます。 最大 50 人のユーザーに通知できます。
7. [**適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsTeamsEmergencyCallingPolicy を参照してください](/powershell/module/skype/new-csteamsemergencycallingpolicy)。

## <a name="edit-an-emergency-calling-policy"></a>緊急通話ポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[音声緊急ポリシー] に移動し、[通話ポリシー] タブ  >  **をクリック** します。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 必要な変更を行い、[適用] を **クリックします**。

### <a name="using-powershell"></a>PowerShell の使用

[「Set-CsTeamsEmergencyCallingPolicy」を参照してください](/powershell/module/skype/set-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>カスタム緊急通話ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallingPolicy も参照してください](/powershell/module/skype/grant-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>ネットワーク サイトにカスタム緊急通話ポリシーを割り当てる

[Set-CsTenantNetworkSite コマンドレット](/powershell/module/skype/set-cstenantnetworksite)を使用して、ネットワーク サイトに緊急通話ポリシーを割り当てる。

次の例では、Contoso 緊急通話ポリシー 1 というポリシーを Site1 サイトに割り当てる方法を示します。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>関連項目

[Teams で緊急通話ルーティング ポリシーを管理する](manage-emergency-call-routing-policies.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)

[ Teams でユーザーにポリシーを割り当てる](assign-policies.md)