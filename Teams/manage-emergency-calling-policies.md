---
title: Microsoft Teams で緊急通報ポリシーを管理する
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
description: Microsoft Teams の緊急通話ポリシーを使用して管理し、組織内の Teams ユーザーが緊急通報を行ったときに何が起こるかを定義する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: a6fa08808c9ef5fc258236735cc043e4bde366b1
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551521"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Microsoft Teams で緊急通報ポリシーを管理する

組織が [PSTN 接続オプション](pstn-connectivity.md)として Microsoft 通話プラン、オペレーター接続、Teams Phone Mobile、またはダイレクト ルーティングを使用している場合は、Microsoft Teams の緊急通話ポリシーを使用して、組織内の Teams ユーザーが緊急通話を行うときの動作を定義できます。

ポリシーを割り当てられたユーザーが緊急サービスを呼び出したときに、通知するユーザーとその通知方法を設定できます。 たとえば、組織のセキュリティ デスクに自動的に通知し、緊急通報でリッスンするようにポリシー設定を構成できます。  

緊急通報ポリシーは、Microsoft Teams 管理センターの **音声** > **緊急ポリシー** に移動するか、Windows PowerShellを使用して管理します。 ポリシーは、ユーザーと [ネットワーク サイト](cloud-voice-network-settings.md)に割り当てることができます。

ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てることができます。 カスタム ポリシーを作成して割り当てる場合を除き、ユーザーはグローバル ポリシーを自動的に取得します。 グローバル ポリシーの設定は編集できますが、名前の変更や削除はできません。 ネットワーク サイトの場合は、カスタム ポリシーを作成して割り当てます。

緊急通話ポリシーをネットワーク サイトとユーザーに割り当て、そのユーザーがそのネットワーク サイトにいる場合、そのネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーよりも優先されます。

## <a name="create-a-custom-emergency-calling-policy"></a>カスタム緊急通報ポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **音声** > **緊急ポリシー** に移動し、[ **通話ポリシー** ] タブをクリックします。

2. **[追加]** をクリックします。

3. ポリシーの名前と説明を入力します。

4. **外部の場所の検索モード** をオンに設定すると、エンド ユーザーが企業ネットワークの外部のネットワークの場所から作業しているときに、緊急アドレスを構成できます。

5. 緊急通報が行われたときに組織内のユーザーに通知する方法 (通常はセキュリティ デスク) を設定します。 これを行うには、[ **通知モード**] で、次のいずれかを選択します。

    - **通知の送信のみ**: Teams チャット メッセージは、指定したユーザーとグループに送信されます。
    - **ミュート状態で会議が行われ、ミュートを解除できません**。Teams チャット メッセージは、指定したユーザーとグループに送信され、発信者と PSAP オペレーターの間の会話でリッスン (ただし参加できません) できます。
    - **ミュート状態で会議が行われますが、ミュートを解除できます**。Teams チャット メッセージは、指定したユーザーとグループに送信され、ミュートを解除して、呼び出し元と PSAP オペレーターの間の会話をリッスンして参加できます。

6.  **緊急サービスの免責事項** を設定してバナーを表示し、緊急の場所を確認するようにエンド ユーザーに通知します。

7.  **いずれかの会議をミュート** 通知モードで選択した場合、[**緊急通報用にダイヤルする番号**] ボックスに、ユーザーまたはグループの PSTN 電話番号を入力して、緊急電話に通話して参加できます。 たとえば、組織のセキュリティ デスクの番号を入力します。緊急通報が行われたときに通話を受け取り、通話をリッスンできます。 モードがミュートで Conferenced に設定されているが **ミュートを解除できる** 場合でも、PSTN 電話のミュートを解除できません。

8. 組織のセキュリティ デスクなどの 1 つ以上のユーザーまたはグループを検索して選択し、緊急通報が行われたときに通知します。  通知は、ユーザー、配布グループ、およびセキュリティ グループの電子メール アドレスに送信できます。 最大 50 人のユーザーに通知できます。

9. [**適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsTeamsEmergencyCallingPolicy を](/powershell/module/skype/new-csteamsemergencycallingpolicy)参照してください。

## <a name="edit-an-emergency-calling-policy"></a>緊急通報ポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **音声** > **緊急ポリシー** に移動し、[ **通話ポリシー** ] タブをクリックします。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 必要な変更を行い、[ **適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[Set-CsTeamsEmergencyCallingPolicy を](/powershell/module/skype/set-csteamsemergencycallingpolicy)参照してください。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>ユーザーにカスタム緊急通報ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy) も参照してください。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>カスタム緊急通報ポリシーをネットワーク サイトに割り当てる

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシーまたは作成した任意のカスタム ポリシーを割り当てることができます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **場所** > **ネットワーク トポロジに** 移動し、[ **ネットワーク サイト** ] タブをクリックします。
2. 名前の左側をクリックしてサイトを選択し、[ **編集]** をクリックします。
3. [ **緊急通報ポリシー**] でポリシーを選択し、[保存] をクリック **します**。

### <a name="using-powershell"></a>PowerShell の使用
[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) コマンドレットを使用して、緊急通話ポリシーをネットワーク サイトに割り当てます。

次の例は、Contoso 緊急通話ポリシー 1 というポリシーを Site1 サイトに割り当てる方法を示しています。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>関連項目

[Teams で緊急通話ルーティング ポリシーを管理する](manage-emergency-call-routing-policies.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)
