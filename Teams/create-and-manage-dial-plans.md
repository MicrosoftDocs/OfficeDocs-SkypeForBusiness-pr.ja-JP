---
title: ダイヤル プランを作成および管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Microsoft Teams 管理センターまたは Windows PowerShellを使用して、ダイヤル プラン (PSTN 通話ダイヤル プラン) を作成および管理する方法について説明します。
ms.openlocfilehash: f94c847f5c75e793856c0975678e2806629e2dcd
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282364"
---
# <a name="create-and-manage-dial-plans"></a>ダイヤル プランを作成および管理する

組織のダイヤル プランを計画し、通話ルーティング用に作成する必要があるすべての正規化ルールを確認したら、ダイヤル プランを作成する準備が整います。 有効な Teams ライセンスを持つ管理者アカウントでは、Microsoft Teams 管理センターまたは Windows PowerShell を使用してダイヤル プランを作成および管理できます。  

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

### <a name="create-a-dial-plan"></a>ダイヤル プランを作成する

1. 管理センターの左側のナビゲーションMicrosoft Teams、Voice Dial **プラン に**  >  **移動します**。
2. [ **追加]** をクリックし、ダイヤル プランの名前と説明を入力します。
    ![ダイヤル プランを作成するための [追加] ページを示すスクリーンショット](media/create-dial-plan.png)
3. [ **ダイヤル プランの詳細**] で、ユーザーが外部行を取得するために 1 つ以上の先頭の数字 (9 など) をダイヤルする必要がある場合は、外部ダイヤル プレフィックスを指定します。 その手順は次のとおりです。
    1. [外部ダイヤル **プレフィックス] ボックスに** 、外部ダイヤル プレフィックスを入力します。 プレフィックスは、最大 4 文字 (#、*、および 0 - 9) で指定できます。
    2. **[Optimized device dialing]をオンにします**。 外部ダイヤル プレフィックスを指定する場合は、組織外で呼び出しを行う前に、この設定を有効にし、プレフィックスを適用する必要があります。
4. [ **正規化ルール] で**、ダイヤル プランの 1 つ [以上の正規化](what-are-dial-plans.md#normalization-rules) ルールを構成して関連付ける。 各ダイヤル プランには、少なくとも 1 つの正規化ルールが関連付けられている必要があります。  これを行うには、次のいずれかの操作を行います。
    - 新しい正規化ルールを作成し、ダイヤル プランに関連付けるには、[追加] をクリックし、ルールを定義します。
    - ダイヤル プランに既に関連付けられている正規化ルールを編集するには、ルール名の左側をクリックしてルールを選択し、[編集] をクリック **します**。 必要な変更を加え、[保存] を **クリックします**。
    - ダイヤル プランから正規化ルールを削除するには、ルール名の左側をクリックしてルールを選択し、[削除] をクリック **します**。
5. 正規化ルールを必要な順序で配置します。 [ **上へ移動]** **または [下** へ移動] をクリックして、リスト内のルールの位置を変更します。

    > [!NOTE]
    > Teams上から下へ正規化ルールの一覧を走査し、ダイヤルされた番号に一致する最初のルールを使用します。 ダイヤルされた番号が複数の正規化ルールと一致できるようダイヤル プランを設定する場合は、制限の厳しいルールを制限の少ないルールよりも上に並べ替える必要があります。

6. **[保存]** をクリックします。
7. ダイヤル プランをテストする場合は、[ダイヤル **プランの** テスト] で電話番号を入力し、[テスト] を **クリックします**。

### <a name="edit-a-dial-plan"></a>ダイヤル プランを編集する

1. 管理センターの左側のナビゲーションMicrosoft Teams、Voice Dial **プラン に**  >  **移動します**。
2. ダイヤル プラン名の左側をクリックしてダイヤル プランを選択し、[編集] をクリック **します**。
3. 必要な変更を行い、[保存] を **クリックします**。

### <a name="assign-a-dial-plan-to-users"></a>ユーザーにダイヤル プランを割り当てる

ポリシーを割り当てるのと同じ方法でダイヤル プランを割り当てる。 [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>PowerShell の使用
  
### <a name="start-powershell"></a>PowerShell を起動する
- コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a>ダイヤル プランの作成と管理

テナント ダイヤル プランを作成および管理するために単一のコマンドレットまたは PowerShell スクリプトのいずれかを使用できます。
  
#### <a name="using-single-cmdlets"></a>単一のコマンドレットの使用

- ダイヤル プランを新規作成するには、次を実行します。
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    その他の例とパラメーターについては、「[New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan)」をご覧ください。
    
- 既存のダイヤル プランの設定を編集するには、次のコマンドを実行します。
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    その他の例とパラメータについては、「[Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan)」をご覧ください。
    
- ユーザーをダイヤル プランに追加するには、次を実行します。
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    その他の例とパラメータについては、「[Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan)」をご覧ください。
    
- ダイヤル プランの設定を表示するには、次を実行します。
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    その他の例とパラメータについては、「[Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps)」をご覧ください。
    
- ダイヤル プランを削除するには、次を実行します。
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    その他の例とパラメータについては、「[Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)」をご覧ください。
    
- 有効なダイヤル プランの設定を表示するには、次を実行します。
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    その他の例とパラメータについては、「[Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan)」をご覧ください。
    
- ダイヤル プランの有効な設定をテストするには、次を実行します。
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    その他の例とパラメータについては、「[Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)」をご覧ください。
    
#### <a name="using-a-powershell-script"></a>PowerShell スクリプトの使用

これを実行して、テナント ダイヤル プランに関連付けられている正規化ルールを削除します。最初にテナント ダイヤル プランを削除する必要があります。
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
これを実行して、次の正規化ルールを RedmondDialPlan という名前の既存のテナント ダイヤル プランに追加します。
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
これを実行して、次の正規化ルールを RedmondDialPlan という名前の既存のテナント ダイヤル プランから削除します。
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

既存の正規化ルールを調べて、どれを削除するかを決定し、そのインデックスを使用して削除するときには、次を実行します。正規化ルールの配列は、インデックス 0 で開始します。インデックス 1 である、3 桁の正規化ルールを削除する必要があります。
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

これを実行して、RedmondDialPlan テナント ダイヤル プランが付与されているすべてのユーザーを見つけます。
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

これを実行して、HostingProvider を持つすべてのユーザーから割り当てられている TenantDialPlan を削除 sipfed.online.lync.com。
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

これらを実行して、OPDP1 という名前の既存のオンプレミス ダイヤル プランを組織のテナント ダイヤル プランとして追加します。まずオンプレミス ダイヤル プランを xml ファイルに保存してから、それを使用して新しいテナント ダイヤル プランを作成する必要があります。
  
これを実行して、オンプレミス ダイヤル プランを xml ファイルに保存します。
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

これを実行して、新しいテナント ダイヤル プランを作成します。
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a>関連トピック

- [ダイヤル プランについて](what-are-dial-plans.md)
- [電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
