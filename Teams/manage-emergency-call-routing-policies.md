---
title: Microsoft Teams で緊急通話ルーティングポリシーを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams の動的 E911 機能の緊急通話ルーティングポリシーの使用方法と管理方法について説明します。
f1keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: e7a1295d481db2d970fae2c77be2cff6834c6448
ms.sourcegitcommit: d349922409f49b52048597a56b81501163749a69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2019
ms.locfileid: "37401832"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Microsoft Teams で緊急通話ルーティングポリシーを管理する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

組織で電話システムのダイレクトルーティングを展開した場合は、Microsoft Teams の緊急通話ルーティングポリシーを使って緊急電話番号を設定し、緊急電話のルーティング方法を指定することができます。 緊急通話ルーティングポリシーは、ポリシーが割り当てられているユーザーに対して強化された緊急サービスが有効になっているかどうかを決定します。また、緊急サービスへの通話に使用する番号 (米国内の911など)、緊急サービスへの通話の発信方法についても説明します。

緊急通話のルーティングポリシーを管理するには、Microsoft Teams 管理センターの**ボイス** > **緊急ポリシー**または Windows PowerShell を使用します。 ポリシーは、ユーザーと[ネットワークサイト](location-based-routing-terminology.md)に割り当てることができます。

ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。 カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを自動的に取得します。 グローバルポリシーの設定は編集できますが、名前の変更や削除はできないことに注意してください。 ネットワークサイトの場合は、カスタムポリシーを作成して割り当てる必要があります。

緊急通話ルーティングポリシーがネットワークサイトとユーザーに割り当てられている場合、そのユーザーがそのネットワークサイトを使用している場合、そのネットワークサイトに割り当てられているポリシーが、ユーザーに割り当てられているポリシーよりも優先されます。

## <a name="create-a-custom-emergency-call-routing-policy"></a>ユーザー設定の緊急通話ルーティングポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス** > **緊急ポリシー**] に移動し、[**通話ルーティングポリシー** ] タブをクリックします。
2. [**追加**] をクリックします。
3. ポリシーの名前と説明を入力します。
4. Enhanced エマージェンシー・サービスを有効にするには、強化された**エマージェンシー・サービス**を有効にします。 強化された緊急サービスが有効になっていると、チームはサービスからポリシーと場所情報を取得し、緊急通話の一部としてその情報を含めます。
5. 緊急電話番号のいずれかを定義します。 これを行うには、[**緊急電話番号**] の下で、次の操作を行います。
    1. **緊急ダイヤル文字列**: 緊急ダイヤルの文字列を入力します。 このダイヤル文字列は、通話が緊急通話であることを示します。
    2. **緊急ダイヤルマスク**: 緊急電話番号ごとに、0個以上の緊急ダイヤルマスクを指定できます。 ダイヤルマスクは、緊急ダイヤルの文字列の値に変換する番号です。 これにより、代替の緊急電話番号にダイヤルすることができます。また、緊急電話サービスにも通話を発信できます。 <br>たとえば、112を緊急ダイヤルのマスクとして追加します。これは、ヨーロッパのほとんどの緊急サービス番号であり、また、緊急ダイヤルの文字列として911です。 他のヨーロッパの Teams ユーザーは、911が米国の緊急電話番号であることを知らない場合があります。また、112の場合は、911に発信されます。 複数のダイヤルマスクを定義するには、各値をセミコロンで区切ります。 たとえば、112; 212 とします。
    3. [ **Pstn 使用状況**]: 公衆交換電話網 (PSTN) 使用量を選択します。 PSTN の使用が許可されているユーザーから緊急通話をルーティングするために使用されるルートを決定するために使用されます。 この使用に関連するルートは、緊急通報専用の SIP トランク、または最も近い公共の安全な応答ポイント (PSAP) に緊急通話をルーティングする緊急電話番号 (ELIN) のゲートウェイを指すようにする必要があります。

    > [!NOTE]
    > ダイヤル文字列とダイヤルマスクは、ポリシー内で一意である必要があります。 つまり、ポリシーの場合、複数の緊急電話番号を定義できますが、ダイヤルする文字列に複数のダイヤルマスクを設定することはできますが、各ダイヤル文字列とダイヤルマスクは1回のみ使用する必要があります。

6. [**保存**] をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する

「[新規-CsTeamsEmergencyCallRoutingPolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)参照してください。

## <a name="edit-an-emergency-call-routing-policy"></a>緊急通話ルーティングポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバルポリシーまたは作成したカスタムポリシーを編集できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス** > **緊急ポリシー**] に移動し、[**通話ルーティングポリシー** ] タブをクリックします。
2. ポリシー名の左側をクリックしてポリシーを選択し、[**編集**] をクリックします。
3. 必要な変更を加えて、[**保存**] をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する

「 [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)」を参照してください。

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>ユーザーにカスタム緊急通話ルーティングポリシーを割り当てる

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. [**ポリシー**] をクリックし、[**割り当てられたポリシー**] の横にある [**編集**] をクリックします。
3. [**緊急着信ルーティングポリシー**] で、割り当てるポリシーを選び、[**保存**] をクリックします。

ユーザー設定のチームポリシーを一度に複数のユーザーに割り当てるには、「 [teams のユーザー設定を一括](edit-user-settings-in-bulk.md)して編集する」を参照してください。

または、次の操作も行うことができます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス** > **緊急ポリシー**] に移動し、[**通話ルーティングポリシー** ] タブをクリックします。
2. ポリシー名の左側をクリックして、ポリシーを選択します。
3. [**ユーザーの管理**] を選びます。
4. [**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] を選択します。 追加するユーザーごとに、この手順を繰り返します。
5. ユーザーの追加が完了したら、[**保存**] をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a>ユーザーにカスタム緊急通話ルーティングポリシーを割り当てる

「 [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)」を参照してください。

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a>ユーザー設定の緊急通話ルーティングポリシーをグループ内のユーザーに割り当てる

ユーザーが既に識別している複数のユーザーに緊急通話ルーティングポリシーを割り当てることができます。 たとえば、セキュリティグループまたは配布グループ内のすべてのユーザーにポリシーを割り当てることができます。 これを行うには、Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続します。

この例では、Contoso の HR グループのすべてのユーザーに、HR 緊急通話ルーティングポリシーと呼ばれるポリシーを割り当てます。  

> [!NOTE]
> 「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。

特定のグループの GroupObjectId を取得します。
```
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
指定したグループのメンバーを取得します。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
グループ内のすべてのユーザーを特定のチームポリシーに割り当てます。 この例では、HR 緊急通話ルーティングポリシーが使用されています。
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.EmailAddress}
``` 
グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>ユーザー設定の緊急通話ルーティングポリシーをネットワークサイトに割り当てる

[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)コマンドレットを使用して、緊急通話ルーティングポリシーをネットワークサイトに割り当てます。

次の例は、緊急通話ルーティングポリシー1と呼ばれるポリシーを Site1 サイトに割り当てる方法を示しています。

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>関連トピック

- [Teams で緊急通話のポリシーを管理する](manage-emergency-calling-policies.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
