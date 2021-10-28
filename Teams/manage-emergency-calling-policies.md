---
title: 緊急通話ポリシーを管理Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams で緊急通話ポリシーを使用および管理して、組織内の Teams ユーザーが緊急通話を行った場合の対応を定義する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 1d4bfe0305939e287c262848dd25665898ba79a6
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605453"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>緊急通話ポリシーを管理Microsoft Teams

組織で PSTN 接続オプションとして Microsoft 通話プラン、オペレーター Connect、または[](pstn-connectivity.md)直接ルーティングを使用している場合は、Microsoft Teams の緊急通話ポリシーを使用して、組織内の Teams ユーザーが緊急通話を行った場合の処理を定義できます。

ポリシーが割り当てられているユーザーが緊急サービスを呼び出したときに通知するユーザーと通知方法を設定できます。 たとえば、ポリシー設定を構成して、組織のセキュリティ デスクに自動的に通知し、緊急通話でリッスンすることができます。  

緊急通話ポリシーを管理するには、Microsoft Teams管理センターで [音声緊急] ポリシーに移動するか  >  、Windows PowerShell。 ポリシーは、ユーザーとネットワーク サイトに [割り当てることができます](cloud-voice-network-settings.md)。

ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。 カスタム ポリシーを作成して割り当てない限り、ユーザーは自動的にグローバル ポリシーを取得します。 グローバル ポリシーの設定は編集できますが、名前の変更や削除はできないので、ご安心ください。 ネットワーク サイトの場合は、カスタム ポリシーを作成して割り当てる必要があります。

緊急通話ポリシーをネットワーク サイトとユーザーに割り当て、そのユーザーがネットワーク サイトにある場合、ネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーを上書きします。

## <a name="create-a-custom-emergency-calling-policy"></a>カスタム緊急通話ポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 管理センターの左側のナビゲーションMicrosoft Teams、[**音声緊急対応** ポリシー] に移動し、[通話ポリシー] タブ  >  **をクリック** します。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。
4. 緊急通話が行われたときに組織内のユーザー (通常はセキュリティ デスク) に通知する方法を設定します。 これを行うには、[通知モード **] で**、次のいずれかを選択します。
    - **通知のみを送信** する: Teamsメッセージが、指定したユーザーとグループに送信されます。
    - **ミュート** 状態で電話会議を行い、ミュートを解除できない: Teams チャット メッセージが、指定したユーザーとグループに送信され、発信者と PSAP オペレーターの間の会話をリッスン (参加できません) できます。
    - **ミュート** で電話会議を行うがミュート解除可能: Teams チャット メッセージが指定したユーザーとグループに送信され、ミュートを解除して発信者と PSAP オペレーター間の会話に参加できます。
5.  いずれかの会議をミュート通知モードで選択した場合は、[緊急通話の通知をダイヤルする番号] ボックスに、緊急通話を発信して参加するユーザーまたはグループの PSTN 電話番号を入力できます。 たとえば、組織のセキュリティ デスクの番号を入力します。緊急通話が行われたときに通話を受け取り、その後、通話をリッスンできます。 モードが [電話会議] にミュートに設定されているが、ミュートを解除できる場合でも、PSTN 電話を **ミュート解除することはできません**。
6. 緊急通話が行われたときに通知する 1 つ以上のユーザーまたはグループ (組織のセキュリティ デスクなど) を検索して選択します。  通知は、ユーザー、配布グループ、およびセキュリティ グループのメール アドレスに送信できます。 最大 50 人のユーザーに通知できます。
7. [**適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsTeamsEmergencyCallingPolicy を参照してください](/powershell/module/skype/new-csteamsemergencycallingpolicy)。

## <a name="edit-an-emergency-calling-policy"></a>緊急通話ポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. 管理センターの左側のナビゲーションMicrosoft Teams、[**音声緊急対応** ポリシー] に移動し、[通話ポリシー] タブ  >  **をクリック** します。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 必要な変更を行い、[適用] を **クリックします**。

### <a name="using-powershell"></a>PowerShell の使用

[「Set-CsTeamsEmergencyCallingPolicy」を参照してください](/powershell/module/skype/set-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>カスタム緊急通話ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallingPolicy も参照してください](/powershell/module/skype/grant-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>ネットワーク サイトにカスタム緊急通話ポリシーを割り当てる

[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)コマンドレットを使用して、緊急通話ポリシーをネットワーク サイトに割り当てる。

次の例は、Contoso 緊急通話ポリシー 1 というポリシーを Site1 サイトに割り当てる方法を示しています。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>関連トピック

[緊急通話ルーティング ポリシーを管理する Teams](manage-emergency-call-routing-policies.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)