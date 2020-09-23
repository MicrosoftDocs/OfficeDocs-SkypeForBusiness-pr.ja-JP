---
title: 緊急通話のルーティング ポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 緊急電話番号を設定し、緊急電話のルーティング方法を指定するために、Microsoft Teams で緊急通話ルーティングポリシーを使用および管理する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 67ef3bb5700c223f3057ef0ba44c9df07a2e7be6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217698"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Microsoft Teams で緊急通話ルーティングポリシーを管理する

組織で [電話システムのダイレクトルーティング](direct-routing-landing-page.md) を展開した場合は、Microsoft Teams の緊急通話ルーティングポリシーを使って緊急電話番号を設定し、緊急電話のルーティング方法を指定することができます。 緊急通話ルーティングポリシーは、ポリシーが割り当てられているユーザーに対して強化された緊急サービスが有効になっているかどうかを決定します。また、緊急サービスへの通話に使用する番号 (米国内の911など)、緊急サービスへの通話の発信方法についても説明します。

緊急通話のルーティングポリシーを管理するに**Voice**  >  は、Microsoft Teams 管理センターのボイス**緊急ポリシー**または Windows PowerShell を使用します。 ポリシーは、ユーザーと [ネットワークサイト](cloud-voice-network-settings.md)に割り当てることができます。

ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。 カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを自動的に取得します。 グローバルポリシーの設定は編集できますが、名前の変更や削除はできないことに注意してください。 ネットワークサイトの場合は、カスタムポリシーを作成して割り当てる必要があります。

緊急通話ルーティングポリシーがネットワークサイトとユーザーに割り当てられている場合、そのユーザーがそのネットワークサイトを使用している場合、そのネットワークサイトに割り当てられているポリシーが、ユーザーに割り当てられているポリシーよりも優先されます。

## <a name="create-a-custom-emergency-call-routing-policy"></a>ユーザー設定の緊急通話ルーティングポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ルーティングポリシー** ] タブをクリックします。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。
4. 動的緊急通話を有効にするには、 **動的緊急通話**を有効にします。 動的な緊急通話が有効になっていると、チームはサービスからポリシーと場所情報を取得し、緊急通話の一部としてその情報を含めます。
5. 1つまたは複数の緊急電話番号を定義します。 これを行うには、[ **緊急電話番号**] の [ **追加**] をクリックし、次の操作を行います。
    1. **緊急ダイヤル文字列**: 緊急ダイヤルの文字列を入力します。 このダイヤル文字列は、通話が緊急通話であることを示します。
        > [!NOTE]
        > ダイレクトルーティングの場合、緊急電話番号の前に「+」を付けて、Teams クライアントから緊急通報に移行しています。 切り替えが完了するまでは、緊急ダイヤルの文字列に一致するボイスルートのパターンによって、911や + 911 などの前に "+" が含まれている文字列に一致していることを確認する必要があります。 たとえば、^ \\ + 911 または. * とします。
    2. **緊急ダイヤルマスク**: 緊急電話番号ごとに、0個以上の緊急ダイヤルマスクを指定できます。 ダイヤルマスクは、緊急ダイヤルの文字列の値に変換する番号です。 これにより、代替の緊急電話番号にダイヤルすることができます。また、緊急電話サービスにも通話を発信できます。 <br>たとえば、112を緊急ダイヤルのマスクとして追加します。これは、ヨーロッパのほとんどの緊急サービス番号であり、また、緊急ダイヤルの文字列として911です。 他のヨーロッパの Teams ユーザーは、911が米国の緊急電話番号であることを知らない場合があります。また、112の場合は、911に発信されます。 複数のダイヤルマスクを定義するには、各値をセミコロンで区切ります。 たとえば、112; 212 とします。
    3. [ **Pstn 使用状況] レコード**: 公衆交換電話網 (PSTN) 利用状況レコードを選択します。 PSTN 使用を許可しているユーザーから緊急電話をルーティングするために使用するルートを決定するために、PSTN 使用状況レコードが使用されます。 この用途に関連付けられているルートは、緊急通報専用のセッション開始プロトコル (SIP) トランク、または最も近い公共の安全な応答ポイント (PSAP) に緊急通話をルーティングする緊急対応の場所識別番号 (ELIN) ゲートウェイを指している必要があります。

    > [!NOTE]
    > ダイヤル文字列とダイヤルマスクは、ポリシー内で一意である必要があります。 つまり、ポリシーの場合、複数の緊急電話番号を定義できますが、ダイヤルする文字列に複数のダイヤルマスクを設定することはできますが、各ダイヤル文字列とダイヤルマスクは1回のみ使用する必要があります。

6. [**保存**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

「 [新規-CsTeamsEmergencyCallRoutingPolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)参照してください。

## <a name="edit-an-emergency-call-routing-policy"></a>緊急通話ルーティングポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ルーティングポリシー** ] タブをクリックします。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 必要な変更を加えて、[ **保存**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

「 [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)」を参照してください。

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>ユーザーにカスタム緊急通話ルーティングポリシーを割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

「 [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)」も参照してください。

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>ユーザー設定の緊急通話ルーティングポリシーをネットワークサイトに割り当てる

[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)コマンドレットを使用して、緊急通話ルーティングポリシーをネットワークサイトに割り当てます。

次の例は、緊急通話ルーティングポリシー1と呼ばれるポリシーを Site1 サイトに割り当てる方法を示しています。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>関連項目

[Teams で緊急通話のポリシーを管理する](manage-emergency-calling-policies.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)

[チームのユーザーにポリシーを割り当てる](assign-policies.md)
