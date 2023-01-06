---
title: Microsoft Teams で緊急通話ポリシーを管理する
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
description: Microsoft Teams で緊急通話ポリシーを使用して管理し、組織内の Teams ユーザーが緊急通報を行った場合の動作を定義する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 1d2dc0e2213f6294e2c596722a4f5ab49bec8487
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727749"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Microsoft Teams で緊急通話ポリシーを管理する

組織で [PSTN 接続オプション](pstn-connectivity.md)として Microsoft 通話プラン、オペレーター接続、Teams Phone Mobile、またはダイレクト ルーティングを使用している場合は、Microsoft Teams の緊急通話ポリシーを使用して、組織内の Teams ユーザーが緊急通話を行うときの動作を定義できます。

通知するユーザーと、ポリシーが割り当てられたユーザーが緊急サービスを呼び出す場合の通知方法を設定できます。 たとえば、組織のセキュリティ デスクに自動的に通知し、緊急通報でリッスンするようにポリシー設定を構成できます。  

緊急通話ポリシーを管理するには、Microsoft Teams 管理センターの **音声** > **緊急ポリシー** に移動するか、Windows PowerShellを使用します。 ポリシーは、ユーザーと [ネットワーク サイト](cloud-voice-network-settings.md)に割り当てることができます。

ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てることができます。 カスタム ポリシーを作成して割り当てない限り、ユーザーはグローバル ポリシーを自動的に取得します。 グローバル ポリシーの設定は編集できますが、名前の変更や削除はできません。 ネットワーク サイトの場合は、カスタム ポリシーを作成して割り当てます。

緊急通話ポリシーをネットワーク サイトとユーザーに割り当て、そのユーザーがそのネットワーク サイトにいる場合、ネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーよりも優先されます。

## <a name="create-a-custom-emergency-calling-policy"></a>カスタム緊急通話ポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ **音声** > **緊急ポリシー**] に移動し、[ **通話ポリシー** ] タブをクリックします。

2. **[追加]** をクリックします。

3. ポリシーの名前と説明を入力します。

4. **[外部の場所の検索モード**] を オンに設定して、エンド ユーザーが会社のネットワーク外のネットワーク上の場所から作業しているときに緊急対応アドレスを構成できるようにします。

5. 緊急通報が行われたときに、組織内のユーザー (通常はセキュリティ デスク) に通知する方法を設定します。 これを行うには、[ **通知モード**] で、次のいずれかを選択します。

    - **通知のみを送信** する: Teams チャット メッセージは、指定したユーザーとグループに送信されます。
    - **会議は行われますがミュート**: Teams チャット メッセージは、指定したユーザーとグループに送信され、呼び出し元と PSAP オペレーターの間の会話でリッスン (参加はしない) ことができます。
    - **会議に参加し、ミュート解除する**: Teams チャット メッセージは、指定したユーザーとグループに送信され、呼び出し元と PSAP オペレーターの間の会話を聞いて参加するためにミュートを解除できます。

6.  **緊急サービスの免責事項** を設定して、緊急対応の場所を確認するようにエンド ユーザーに通知するバナーを表示します。

7.  ミュート通知モード **でいずれかの会議** を選択した場合は、[ **緊急通報の通知にダイヤルする番号** ] ボックスに、緊急通報を呼び出して参加するユーザーまたはグループの PSTN 電話番号を入力できます。 たとえば、緊急通報が行われたときに通話を受け取り、通話をリッスンできる組織のセキュリティ デスクの番号を入力します。 モードがミュート状態で Conferenced に設定されていても、ミュートを解除できる場合でも、PSTN 電話 **をミュート解除することはできません**。

8. 緊急通報が行われたときに通知するユーザー (セキュリティ デスク担当者など) を設定します。 ユーザー、配布グループ、またはセキュリティ グループの一覧を定義できます。 最大 50 人のユーザーに通知できます。

9. [**適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[「New-CsTeamsEmergencyCallingPolicy」を参照](/powershell/module/skype/new-csteamsemergencycallingpolicy)してください。

## <a name="edit-an-emergency-calling-policy"></a>緊急通報ポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[ **音声** > **緊急ポリシー**] に移動し、[ **通話ポリシー** ] タブをクリックします。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 必要な変更を行い、[ **適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[「Set-CsTeamsEmergencyCallingPolicy」を参照](/powershell/module/skype/set-csteamsemergencycallingpolicy)してください。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>カスタム緊急通話ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[「Grant-CsTeamsEmergencyCallingPolicy」](/powershell/module/skype/grant-csteamsemergencycallingpolicy)も参照してください。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>カスタム緊急通話ポリシーをネットワーク サイトに割り当てる

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシーまたは作成したカスタム ポリシーを割り当てることができます。

1. Microsoft Teams 管理センターの左側のナビゲーションで、[場所 **] [ネットワーク トポロジ****]** >  に移動し、[**ネットワーク サイト**] タブをクリックします。
2. 名前の左側をクリックしてサイトを選択し、[ **編集**] をクリックします。
3. [ **緊急通話ポリシー**] でポリシーを選択し、[ **保存**] をクリックします。

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
