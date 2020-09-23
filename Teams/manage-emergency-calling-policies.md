---
title: Microsoft Teams で緊急通話ポリシーを管理する
author: lanachin
ms.author: v-lanac
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
description: Microsoft Teams で緊急通話ポリシーを使用して管理する方法について説明します。この方法では、組織内の Teams ユーザーが緊急通報を行ったときの動作を定義します。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: ac2c06e9ba93e650909ee776383f1cebd9da1a9d
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217668"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Microsoft Teams で緊急通話ポリシーを管理する

組織で [通話プラン](set-up-calling-plans.md) を使用している場合、または [電話システムダイレクトルーティング](direct-routing-landing-page.md)を展開している場合は、Microsoft teams の緊急通話ポリシーを使用して、組織内の Teams ユーザーが緊急通報を行ったときの動作を定義できます。 ポリシーを割り当てられたユーザーが緊急サービスを呼び出すときの通知方法と通知方法を設定することができます。 たとえば、ポリシー設定を構成して、組織のセキュリティデスクに自動的に通知し、緊急通話で聞くことができます。  

緊急通話のポリシーを管理するに**Voice**  >  は、Microsoft Teams 管理センターのボイス**緊急ポリシー**または Windows PowerShell を使用します。 ポリシーは、ユーザーと [ネットワークサイト](cloud-voice-network-settings.md)に割り当てることができます。

ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。 カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを自動的に取得します。 グローバルポリシーの設定は編集できますが、名前の変更や削除はできないことに注意してください。 ネットワークサイトの場合は、カスタムポリシーを作成して割り当てる必要があります。

緊急通話のポリシーをネットワークサイトとユーザーに割り当てている場合、そのユーザーがそのネットワークサイトを使用している場合は、そのネットワークサイトに割り当てられているポリシーが、ユーザーに割り当てられているポリシーよりも優先されます。

## <a name="create-a-custom-emergency-calling-policy"></a>ユーザー設定の緊急通話ポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ポリシー** ] タブをクリックします。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。
4. 緊急通報が行われたときに、組織内のユーザーに通知する方法 (通常はセキュリティデスク) を設定します。 これを行うには、[ **通知モード**] で、次のいずれかを選択します。
    - **通知のみ送信**: チームチャットメッセージは、指定したユーザーとグループに送信されます。
    - **Conferenced がミュートになっている**場合: チームチャットメッセージは、指定したユーザーとグループに送信され、発信者と psap 演算子の間の会話に参加することはできますが、参加することはできません。
    - **Conferenced in and is ミュート** **(近**日公開): チームチャットメッセージは指定したユーザーとグループに送信され、ミュートを解除して、発信者と psap 演算子の間の会話に参加することができます。
5.  Conferenced を選択した **が** 、[ **緊急通話にダイヤルする番号** ] がオンになっている場合は、ユーザーまたはグループの PSTN 電話番号を入力して、通話を発信し、緊急通話に参加することができます。 たとえば、組織のセキュリティデスクの番号を入力すると、緊急通話の発信時に通話を受けられ、通話を聞くことができます。
6. 緊急通報が行われたときに通知するために、1人以上のユーザーまたはグループ (組織のセキュリティデスクなど) を検索して選択します。  通知は、ユーザー、配布グループ、セキュリティグループのメールアドレスに送信できます。 通知できるユーザーの最大数は50です。
7. [**適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

「 [新規-CsTeamsEmergencyCallingPolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)参照してください。

## <a name="edit-an-emergency-calling-policy"></a>緊急通話のポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ポリシー** ] タブをクリックします。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 必要な変更を加えて、[ **適用**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

「 [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)」を参照してください。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>ユーザーにカスタム緊急通話ポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

「 [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)」も参照してください。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>ユーザー設定の緊急通話ポリシーをネットワークサイトに割り当てる

[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)コマンドレットを使用して、緊急通話ポリシーをネットワークサイトに割り当てます。

次の例は、Contoso 緊急通話ポリシー1と呼ばれるポリシーを Site1 サイトに割り当てる方法を示しています。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>関連項目

[Teams で緊急通話ルーティングポリシーを管理する](manage-emergency-call-routing-policies.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)

[チームのユーザーにポリシーを割り当てる](assign-policies.md)
