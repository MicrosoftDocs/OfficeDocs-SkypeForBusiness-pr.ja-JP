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
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams で緊急通話ポリシーを使用して管理する方法について説明します。この方法では、組織内の Teams ユーザーが緊急通報を行ったときの動作を定義します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea02c1c7f9d4142db9cb25c00714e04a28e0e5e3
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350201"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Microsoft Teams で緊急通話ポリシーを管理する

組織で通話プランを使用している場合、または電話システムダイレクトルーティングを展開している場合は、Microsoft Teams の緊急通話ポリシーを使用して、組織内の Teams ユーザーが緊急通報を行ったときの動作を定義できます。 ポリシーを割り当てられたユーザーが緊急サービスを呼び出すときの通知方法と通知方法を設定することができます。 たとえば、ポリシー設定を構成して、組織のセキュリティデスクに自動的に通知し、緊急通話で聞くことができます。  

緊急通話のポリシーを管理するに**Voice**  >  は、Microsoft Teams 管理センターのボイス**緊急ポリシー**または Windows PowerShell を使用します。 ポリシーは、ユーザーと[ネットワークサイト](cloud-voice-network-settings.md)に割り当てることができます。

ユーザーの場合は、グローバル (組織全体の既定) ポリシーを使用するか、カスタムポリシーを作成して割り当てることができます。 カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを自動的に取得します。 グローバルポリシーの設定は編集できますが、名前の変更や削除はできないことに注意してください。 ネットワークサイトの場合は、カスタムポリシーを作成して割り当てる必要があります。

緊急通話のポリシーをネットワークサイトとユーザーに割り当てている場合、そのユーザーがそのネットワークサイトを使用している場合は、そのネットワークサイトに割り当てられているポリシーが、ユーザーに割り当てられているポリシーよりも優先されます。

## <a name="create-a-custom-emergency-calling-policy"></a>ユーザー設定の緊急通話ポリシーを作成する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ポリシー** ] タブをクリックします。
2. **[追加]** をクリックします。
3. ポリシーの名前と説明を入力します。
4. 緊急通報が行われたときに、組織内のユーザーに通知する方法 (通常はセキュリティデスク) を設定します。 これを行うには、[**通知モード**] で、次のいずれかを選択します。
    - **通知のみ送信**: チームチャットメッセージは、指定したユーザーとグループに送信されます。
    - **Conferenced がミュートになっている**場合: チームチャットメッセージは、指定したユーザーとグループに送信され、発信者と psap 演算子の間の会話に参加することはできますが、参加することはできません。
    - **Conferenced in and is ミュート** **(近**日公開): チームチャットメッセージは指定したユーザーとグループに送信され、ミュートを解除して、発信者と psap 演算子の間の会話に参加することができます。
5.  Conferenced を選択した**が、ミュート**の通知モードの場合は、[**通知のダイヤルアウト番号**] ボックスで、ユーザーまたはグループの PSTN 電話番号を入力して、通話を発信し、緊急通話に参加することができます。 たとえば、組織のセキュリティデスクの番号を入力すると、緊急通話の発信時に通話を受けられ、通話を聞くことができます。
6. 緊急通報が行われたときに通知するために、1人以上のユーザーまたはグループ (組織のセキュリティデスクなど) を検索して選択します。  通知は、ユーザー、配布グループ、セキュリティグループのメールアドレスに送信できます。 通知できるユーザーの最大数は50です。
7. **[保存]** をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する場合

「[新規-CsTeamsEmergencyCallingPolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)参照してください。

## <a name="edit-an-emergency-calling-policy"></a>緊急通話のポリシーを編集する

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

グローバル ポリシー、または作成したカスタム ポリシーを編集できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ポリシー** ] タブをクリックします。
2. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。
3. 必要な変更を加えて、[**保存**] をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する場合

「 [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)」を参照してください。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>ユーザーにカスタム緊急通話ポリシーを割り当てる

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1人のユーザーにポリシーを割り当てるには、次の操作を行います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. **[ポリシー]** をクリックし、**[割り当てられたポリシー]** の横にある **[編集]** をクリックします。
3. [**緊急通話ポリシー**] で、割り当てるポリシーを選択し、[**保存**] をクリックします。

複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。

1. Microsoft Teams 管理センターの左のナビゲーションで [**ユーザー**] に移動し、ユーザーを検索するか、ビューをフィルター処理して、目的のユーザーを表示します。
2. [ **&#x2713;** (チェックマーク)] 列で、ユーザーを選びます。 すべてのユーザーを選択するには、テーブルの上部にある &#x2713; (チェックマーク) をクリックします。
3. [**設定の編集**] をクリックし、必要な変更を加えて、[**適用**] をクリックします。  

または、次の操作も実行できます。

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **緊急ポリシー**] に移動し、[**通話ポリシー** ] タブをクリックします。
2. ポリシー名の左側をクリックしてポリシーを選びます。
3. [**ユーザーを管理**] を選択します。
4. [**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。 追加するユーザーごとに、この手順を繰り返します。
5. ユーザーの追加が完了したら、[**保存**] をクリックします。

### <a name="using-powershell"></a>PowerShell を使用する場合

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a>ユーザーにカスタム緊急通話ポリシーを割り当てる

「 [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)」を参照してください。

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a>ユーザー設定の緊急通話ポリシーをグループ内のユーザーに割り当てる

複数のユーザーに対して、既に特定した緊急通話のポリシーを割り当てることができます。 たとえば、セキュリティ グループのすべてのユーザーにポリシーを割り当てることができます。 これを行うには、Graph 用 Azure Active Directory PowerShell モジュールと Skype for Business PowerShell モジュールに接続します。

この例では、[Contoso の運営] グループのすべてのユーザーに、[操作緊急通話] ポリシーと呼ばれるポリシーを割り当てます。  

> [!NOTE]
> 「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」の手順に従って、必ず最初に Azure Active Directory PowerShell for Graph モジュールと Skype for Business PowerShell モジュールに接続してください。

特定のグループの GroupObjectId を取得します。
```powershell
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
指定したグループのメンバーを取得します。
```powershell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
グループ内のすべてのユーザーを特定のチーム ポリシーに割り当てる。 この例では、操作は緊急通話ルーティングポリシーです。
```powershell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
グループ内のメンバー数によっては、このコマンドの実行に数分かかる場合があります。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>ユーザー設定の緊急通話ポリシーをネットワークサイトに割り当てる

[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)コマンドレットを使用して、緊急通話ポリシーをネットワークサイトに割り当てます。

次の例は、Contoso 緊急通話ポリシー1と呼ばれるポリシーを Site1 サイトに割り当てる方法を示しています。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>関連トピック

- [Teams で緊急通話ルーティングポリシーを管理する](manage-emergency-call-routing-policies.md)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
- [チームのユーザーにポリシーを割り当てる](assign-policies.md)
