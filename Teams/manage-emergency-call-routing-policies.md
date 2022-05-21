---
title: ダイレクト ルーティングの緊急通話ルーティング ポリシーを管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teamsの緊急通報ルーティング ポリシーを使用して管理し、緊急電話番号を設定し、緊急通報のルーティング方法を指定する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 33a0493d038586aa51daf29e320e9ffa9c6c7b5b
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624121"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a>ダイレクト ルーティングの緊急通話ルーティング ポリシーを管理する

組織内に[ダイレクト ルーティング](direct-routing-landing-page.md)を展開した場合は、Microsoft Teamsで緊急通報ルーティング ポリシーを使用して緊急電話番号を設定し、緊急通報のルーティング方法を指定できます。 緊急通話ルーティング ポリシーは、ポリシーが割り当てられているユーザーに対して強化された緊急サービスを有効にするかどうか、緊急サービスの呼び出しに使用される番号 (米国の 911 など)、および緊急サービスへの通話のルーティング方法を決定します。 

> [!Note]
> **これらの呼び出しルーティング ポリシーは、直接ルーティングにのみ適用されることに注意してください。通話プランまたはオペレーター接続には適用されません。**

緊急通話ルーティング ポリシーは、Microsoft Teams管理センターの **VoiceEmergency**  >  ポリシーに移動するか、Windows PowerShellを使用して管理します。 ポリシーは、ユーザーと [ネットワーク サイト](cloud-voice-network-settings.md)に割り当てることができます。

ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てることができます。 カスタム ポリシーを作成して割り当てる場合を除き、ユーザーはグローバル ポリシーを自動的に取得します。 グローバル ポリシーの設定は編集できますが、名前の変更や削除はできません。 ネットワーク サイトの場合は、カスタム ポリシーを作成して割り当てます。

緊急通話ルーティング ポリシーをネットワーク サイトとユーザーに割り当て、そのユーザーがそのネットワーク サイトにいる場合、そのネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーよりも優先されます。

## <a name="create-a-custom-emergency-call-routing-policy"></a>カスタム緊急通報ルーティング ポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceEmergency** >  ポリシーに移動し、[**通話ルーティング ポリシー**] タブをクリックします。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。
4. 動的緊急通報を有効にするには、 **動的緊急通報を** 有効にします。 動的緊急通報が有効になっている場合、Teamsはサービスからポリシーと場所の情報を取得し、緊急通報の一部としてその情報を含めます。
5. 1 つ以上の緊急電話番号を定義します。 これを行うには、[ **緊急電話番号**] で [ **追加**] をクリックし、次の操作を行います。
    1. **緊急ダイヤル文字列**: 緊急ダイヤル文字列を入力します。 このダイヤル文字列は、通話が緊急通話であり、ルート パターンがこのダイヤル文字列と正確に一致する必要があることを示します。 
        > [!NOTE]
        > **ダイレクト ルーティングの場合、Teams クライアントは緊急ダイヤル文字列の前に "+" を含む緊急通話を送信しなくなりました。緊急ダイヤル文字列と一致する音声ルート パターンに、この変更が反映されていることを確認します。**
    2. **緊急ダイヤル マスク**: 緊急電話番号ごとに、0 個以上の緊急ダイヤル マスクを指定できます。 ダイヤル マスクは、緊急ダイヤル文字列の値に変換する番号です。 これにより、代替の緊急電話番号をダイヤルし、通話が緊急サービスに届きます。 <br>たとえば、緊急ダイヤル マスクとして 112 を追加します。これはほとんどのヨーロッパの緊急サービス番号で、緊急ダイヤル文字列として 911 を追加します。 ヨーロッパからのTeams ユーザーが、911 が米国の緊急電話番号であることを知らない場合があり、112 にダイヤルすると、911 に通話が発信されます。 複数のダイヤル マスクを定義するには、各値をセミコロンで区切ります。 たとえば、112;212 です。
    3. **PSTN 使用法レコード**: 公衆交換電話網 (PSTN) の使用レコードを選択します。 PSTN 使用法レコードは、使用が承認されているユーザーからの緊急通話のルーティングに使用されるルートを決定するために使用されます。 この使用法に関連付けられているルートは、緊急通報専用のセッション開始プロトコル (SIP) トランク、または緊急通報を最も近い公衆安全応答ポイント (PSAP) にルーティングする緊急場所識別番号 (ELIN) ゲートウェイを指す必要があります。

    > [!NOTE]
    > ダイヤル文字列とダイヤル マスクは、ポリシー内で一意である必要があります。 つまり、ポリシーでは複数の緊急電話番号を定義でき、ダイヤル文字列に複数のダイヤル マスクを設定できますが、各ダイヤル文字列とダイヤル マスクは 1 回だけ使用する必要があります。

6. **[保存]** をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsTeamsEmergencyCallRoutingPolicy を](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)参照してください。

## <a name="edit-an-emergency-call-routing-policy"></a>緊急通報ルーティング ポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams管理センターの左側のナビゲーションで、**VoiceEmergency** >  ポリシーに移動し、[**通話ルーティング ポリシー**] タブをクリックします。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 必要な変更を加え、[保存] をクリック **します**。

### <a name="using-powershell"></a>PowerShell の使用

[Set-CsTeamsEmergencyCallRoutingPolicy に関するページを参照](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)してください。

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>カスタム緊急通報ルーティング ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy) も参照してください。

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>カスタム緊急通報ルーティング ポリシーをネットワーク サイトに割り当てる

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシーまたは作成した任意のカスタム ポリシーを割り当てることができます。

1. Microsoft Teams管理センターの左側のナビゲーションで、**LocationsNetwork** >  **トポロジに** 移動し、[**ネットワーク サイト**] タブをクリックします。
2. 名前の左側をクリックしてサイトを選択し、[ **編集]** をクリックします。
3. [ **緊急通話ルーティング ポリシー**] でポリシーを選択し、[ **保存**] をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) コマンドレットを使用して、緊急通話ルーティング ポリシーをネットワーク サイトに割り当てます。

この例では、緊急通話ルーティング ポリシー 1 というポリシーを Site1 サイトに割り当てる方法を示します。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>関連項目

[Teamsで緊急通報ポリシーを管理する](manage-emergency-calling-policies.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)

[ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)
