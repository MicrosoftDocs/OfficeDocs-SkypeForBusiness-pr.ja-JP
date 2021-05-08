---
title: 緊急通話のルーティング ポリシーを管理する
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で緊急通話ルーティング ポリシーを使用および管理して緊急電話番号を設定し、緊急通話のルーティング方法を指定する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 0fb3a80bf5c1a064435754c4f999f6a62214b021
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096181"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>緊急通話ルーティング ポリシーを管理Microsoft Teams

組織内に[電話システム ダイレクト](direct-routing-landing-page.md)ルーティングをデプロイしている場合は、Microsoft Teams の緊急通話ルーティング ポリシーを使用して緊急電話番号を設定し、緊急通話のルーティング方法を指定できます。 緊急通話ルーティング ポリシーは、ポリシーが割り当てられているユーザーに対して強化された緊急サービスを有効にするかどうか、緊急サービスの呼び出しに使用される番号 (米国では 911 など)、緊急サービスへの呼び出しのルーティング方法を決定します。

緊急通話ルーティング ポリシーを管理するには、Microsoft Teams管理センターで音声緊急ポリシーに移動するか  >  、Windows PowerShell。 ポリシーは、ユーザーとネットワーク サイトに [割り当てることができます](cloud-voice-network-settings.md)。

ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。 カスタム ポリシーを作成して割り当てない限り、ユーザーは自動的にグローバル ポリシーを取得します。 グローバル ポリシーの設定は編集できますが、名前の変更や削除はできないので、ご安心ください。 ネットワーク サイトの場合は、カスタム ポリシーを作成して割り当てる必要があります。

緊急通話ルーティング ポリシーをネットワーク サイトとユーザーに割り当て、そのユーザーがネットワーク サイトに割り当てられている場合、ネットワーク サイトに割り当てられているポリシーは、ユーザーに割り当てられているポリシーを上書きします。

## <a name="create-a-custom-emergency-call-routing-policy"></a>カスタム緊急通話ルーティング ポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 管理センターの左側のナビゲーションMicrosoft Teams[**音声緊急対応** ポリシー] に移動し、[通話ルーティング ポリシー] タブ  >  **をクリック** します。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。
4. 動的緊急通話を有効にするには、動的緊急通話 **を有効にしてください**。 動的緊急通話が有効になっている場合、Teams サービスからポリシーと場所の情報を取得し、その情報を緊急通話の一部として含める必要があります。
5. 1 つ以上の緊急電話番号を定義します。 これを行うには、[緊急電話番号] **で**[追加] を **クリックし**、次の操作を行います。
    1. **[緊急ダイヤル文字列**]: 緊急ダイヤル文字列を入力します。 このダイヤル文字列は、通話が緊急通話を示します。
        > [!NOTE]
        > ダイレクト ルーティングでは、緊急ダイヤル文字列の前に "+" Teams を使用して緊急通話を送信するクライアントから移行します。 切り替えが完了するまで、緊急ダイヤル文字列に一致する音声ルート パターンは、911 や +911 など、前の "+" を持つ文字列とない文字列に対して一致が行われます。 例: ^ \\ +?911 または .*。
    2. **緊急ダイヤル マスク**: 緊急電話番号ごとに、0 個以上の緊急ダイヤル マスクを指定できます。 ダイヤル マスクは、緊急ダイヤル文字列の値に変換する番号です。 これにより、代替の緊急電話番号をダイヤルし、通話が緊急サービスに届く可能性があります。 <br>たとえば、緊急ダイヤル マスクとして 112 を追加します。これはヨーロッパの大部分の緊急サービス番号で、911 を緊急ダイヤル文字列として追加します。 ヨーロッパTeamsしているユーザーは、911 が米国の緊急電話番号であり、112 をダイヤルすると 911 に発信されます。 複数のダイヤル マスクを定義するには、各値をセミコロンで区切ります。 たとえば、112;212 です。
    3. **PSTN 使用レコード**: 公衆交換電話網 (PSTN) 使用レコードを選択します。 PSTN 使用状況レコードは、使用が承認されているユーザーからの緊急通話をルーティングするために使用されるルートを決定するために使用されます。 この使用に関連付けられているルートは、緊急通話専用のセッション開始プロトコル (SIP) トランク、または緊急通話を最も近い公衆安全応答ポイント (PSAP) にルーティングする緊急場所識別番号 (ELIN) ゲートウェイを指す必要があります。

    > [!NOTE]
    > ダイヤル文字列とダイヤル マスクは、ポリシー内で一意である必要があります。 つまり、ポリシーでは複数の緊急電話番号を定義し、ダイヤル文字列に複数のダイヤル マスクを設定できますが、各ダイヤル文字列とダイヤル マスクは 1 回のみ使用する必要があります。

6. **[保存]** をクリックします。

### <a name="using-powershell"></a>PowerShell の使用

[New-CsTeamsEmergencyCallRoutingPolicy を参照してください](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)。

## <a name="edit-an-emergency-call-routing-policy"></a>緊急通話ルーティング ポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. 管理センターの左側のナビゲーションMicrosoft Teams[**音声緊急対応** ポリシー] に移動し、[通話ルーティング ポリシー] タブ  >  **をクリック** します。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 必要な変更を行い、[保存] を **クリックします**。

### <a name="using-powershell"></a>PowerShell の使用

[「Set-CsTeamsEmergencyCallRoutingPolicy」を参照してください](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>カスタム緊急通話ルーティング ポリシーをユーザーに割り当てる

[!INCLUDE [assign-policy](includes/assign-policy.md)]

[Grant-CsTeamsEmergencyCallRoutingPolicy も参照してください](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)。

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>カスタム緊急通話ルーティング ポリシーをネットワーク サイトに割り当てる

[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)コマンドレットを使用して、緊急通話ルーティング ポリシーをネットワーク サイトに割り当てる。

この例では、緊急通話ルーティング ポリシー 1 というポリシーを Site1 サイトに割り当てる方法を示します。

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>関連トピック

[緊急通話ポリシーを管理Teams](manage-emergency-calling-policies.md)

[Teams での PowerShell の概要](teams-powershell-overview.md)

[ Teams でユーザーにポリシーを割り当てる](assign-policies.md)