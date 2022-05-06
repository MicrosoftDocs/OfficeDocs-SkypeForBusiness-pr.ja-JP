---
title: Microsoft Teamsで緊急通報ポリシーを管理する
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
description: Microsoft Teamsで緊急通報ポリシーを使用して管理し、組織内のTeamsユーザーが緊急通報を行ったときに何が起こるかを定義する方法について説明します。
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
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Microsoft Teamsで緊急通報ポリシーを管理する

組織が [PSTN 接続オプション](pstn-connectivity.md)として Microsoft 通話プラン、オペレーター接続、またはダイレクト ルーティングを使用している場合は、Microsoft Teamsで緊急通話ポリシーを使用して、組織内のTeams ユーザーが緊急通話を行った場合の動作を定義できます。

ポリシーを割り当てられたユーザーが緊急サービスを呼び出したときに、通知するユーザーとその通知方法を設定できます。 たとえば、組織のセキュリティ デスクに自動的に通知し、緊急通報でリッスンするようにポリシー設定を構成できます。  

緊急通報ポリシーは、Microsoft Teams管理センターの **VoiceEmergency**  >  ポリシーに移動するか、Windows PowerShellを使用して管理します。 ポリシーは、ユーザーと [ネットワーク サイト](cloud-voice-network-settings.md)に割り当てることができます。

ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てることができます。 カスタム ポリシーを作成して割り当てる場合を除き、ユーザーはグローバル ポリシーを自動的に取得します。 グローバル ポリシーの設定は編集できますが、名前の変更や削除はできません。 ネットワーク サイトの場合は、カスタム ポリシーを作成して割り当てます。

緊急通話ポリシーをネットワーク サイトとユーザーに割り当て、そのユーザーがそのネットワーク サイトにいる場合、そのネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーよりも優先されます。

## <a name="create-a-custom-emergency-calling-policy"></a>カスタム緊急通報ポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceEmergency** >  ポリシーに移動し、[**通話ポリシー**] タブをクリックします。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。
4. 緊急通報が行われたときに組織内のユーザーに通知する方法 (通常はセキュリティ デスク) を設定します。 これを行うには、[ **通知モード**] で、次のいずれかを選択します。
    - **通知の送信のみ**: Teams チャット メッセージは、指定したユーザーとグループに送信されます。
    - **ミュート状態で会議が行われ、ミュートを解除できません**。 Teams チャット メッセージは、指定したユーザーとグループに送信され、発信者と PSAP オペレーターの間の会話でリッスン (ただし参加できません) できます。
    - **ミュート状態で会議が行われますが、ミュートを解除できます**。 Teams チャット メッセージは、指定したユーザーとグループに送信され、ミュートを解除して、呼び出し元と PSAP オペレーターの間の会話をリッスンして参加できます。
5.  **いずれかの会議をミュート** 通知モードで選択した場合、[**緊急通報用にダイヤルする番号**] ボックスに、ユーザーまたはグループの PSTN 電話番号を入力して、緊急電話に通話して参加できます。 たとえば、組織のセキュリティ デスクの番号を入力します。緊急通報が行われたときに通話を受け取り、通話をリッスンできます。 モードがミュートで Conferenced に設定されているが **ミュートを解除できる** 場合でも、PSTN 電話のミュートを解除できません。
6. 組織のセキュリティ デスクなどの 1 つ以上のユーザーまたはグループを検索して選択し、緊急通報が行われたときに通知します。  通知は、ユーザー、配布グループ、およびセキュリティ グループの電子メール アドレスに送信できます。 最大 50 人のユーザーに通知できます。
7. [**適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsTeamsEmergencyCallingPolicy を](/powershell/module/skype/new-csteamsemergencycallingpolicy)参照してください。

## <a name="edit-an-emergency-calling-policy"></a>緊急通報ポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceEmergency** >  ポリシーに移動し、[**通話ポリシー**] タブをクリックします。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 必要な変更を行い、[ **適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[Set-CsTeamsEmergencyCallingPolicy を](/powershell/module/skype/set-csteamsemergencycallingpolicy)参照してください。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>ユーザーにカスタム緊急通報ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy) も参照してください。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>カスタム緊急通報ポリシーをネットワーク サイトに割り当てる

[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) コマンドレットを使用して、緊急通話ポリシーをネットワーク サイトに割り当てます。

次の例は、Contoso 緊急通話ポリシー 1 というポリシーを Site1 サイトに割り当てる方法を示しています。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>関連項目

[Teamsで緊急通話ルーティング ポリシーを管理する](manage-emergency-call-routing-policies.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)