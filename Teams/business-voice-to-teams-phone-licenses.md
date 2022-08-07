---
title: Business Voice から Teams Phone ライセンスに移行する
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
description: Business Voice ライセンスを Teams Phone ライセンスに変更する方法について説明します。
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 6e7622e4b78e57f45209b90a525eb5fefbe8cd66
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271232"
---
# <a name="move-from-business-voice-to-teams-phone-licenses"></a>Business Voice から Teams Phone ライセンスに移行する

2022 年 6 月の終わりまでに Business Voice は廃止されます。そのため、[通話プラン付き Microsoft Teams 電話 バンドル ライセンスに切り替える企業をお勧めします](https://techcommunity.microsoft.com/t5/small-and-medium-business-blog/teams-phone-with-calling-plan-available-in-33-markets-on-january/ba-p/2967643)。

Business Voice には、次の 3 つの Teams アドオン ライセンスがバンドルされています。

- Microsoft Teams のクラウドベースの電話システムの **Microsoft Teams 電話**。
- **会議** のダイヤルインおよびダイヤルアウト会議用の電話会議。
- 公衆交換電話網 (PSTN) 接続に対する国内通話の **Microsoft 通話プラン**。

既存の Business Voice のお客様は、新しいライセンス モデルに自動的に移行されません。

この記事は、同じ機能を維持しながら、Business Voice ライセンスを Microsoft Teams 電話 ライセンスと電話会議ライセンスに変更する必要がある IT 管理者向けです。

> [!WARNING]
> この記事の手順に密接に従ってください。 指示に従って **[保存** ] ボタンを選択しないように指示されている場合は、[ **保存]** ボタンを選択しないでください。
>
> 途中で保存すると、電話番号の割り当て、ダイヤル プラン、自動応答、通話キューが失われる可能性があります。

## <a name="acquire-new-licenses"></a>新しいライセンスを取得する

Business Voice ライセンスを置き換える前に、まずユーザーの代替ライセンスを購入する必要があります。

これらの機能を提供するには、ライセンスが必要です。

- 電話会議
- クラウドベースの電話システム
- PSTN 接続

次の表を使用して、ニーズに基づいて購入するライセンスを決定します。

| 古いライセンス プラン | 推奨されるライセンス プラン | 説明 |
| ---------------- | ------------------------ | ----------- |
| 通話プラン付き Business Voice | 通話プランを使用した Teams Phone と、USA/CAN へのダイヤルアウトを使用したMicrosoft Teams 電話会議 | クラウドベースの電話システム機能、PSTN プロバイダーとして Microsoft を使用した国内通話プラン、ライセンスユーザーが組織した出席者へのダイヤルインおよびダイヤルアウト機能を提供します。 |
| 通話プランのないビジネス音声 | USA/CAN へのダイヤルアウトを使用したTeams 電話スタンダードとMicrosoft Teams 電話会議 | [オペレーター接続またはダイレクト ルーティングを使用して PSTN プロバイダーとサード パーティ通話プランと](pstn-connectivity.md)組み合わせることができるクラウドベースの電話システム機能を提供し、ライセンスを持つユーザーが組織する出席者にダイヤルインおよびダイヤルアウト機能を提供します。 |

## <a name="how-to-update-licenses"></a>ライセンスを更新する方法

ライセンスを更新するには、次の 4 つの方法があります。

- Microsoft 365 管理センターによるシングル ユーザー ライセンスの更新
- Microsoft 365 管理センターを使用した一括ユーザー ライセンスの更新
- PowerShell スクリプトを使用したユーザー ライセンスの一括更新
- Azure グループ ベースのライセンスを使用した一括ユーザー ライセンスの更新

# <a name="option-1-single-user-in-admin-center"></a>[オプション 1: 管理センターの 1 人のユーザー](#tab/single-user)

### <a name="option-1-single-user-license-update-via-microsoft-365-admin-center"></a>オプション 1: Microsoft 365 管理センターによるシングル ユーザー ライセンスの更新

1 人のユーザーを更新するには、Microsoft 365 管理センターを使用できます。

1. [admin.microsoft.com](https://admin.microsoft.com/) に移動し、テナント管理者の資格情報でサインインします。
1. **[ユーザー****アクティブ ユーザー]** >  に移動し、目的のユーザーを選択します。
1. リスト ツール バーの [ **製品ライセンスの管理** ] を選択します。
1. [ **ライセンスとアプリ** ] 画面で、Business Voice ライセンスの選択を解除します。
    > [!IMPORTANT]
    > 変更をまだ保存しないでください。 新しいライセンスを追加せずに変更を保存すると、ユーザー アカウントはプロビジョニング解除され、電話番号は割り当て解除されます。
1. Business Voice の選択を解除した後、新しい Teams Phone および Audio Conferencing ライセンスを確認します。
1. これで、[変更の保存] を選択して、変更を安全 **に保存** できます。

ユーザーのライセンスは更新され、サービスの可用性には影響しません。

# <a name="option-2-bulk-users-in-admin-center"></a>[オプション 2: 管理センターの一括ユーザー](#tab/bulk-users-admin-center)

### <a name="option-2-bulk-user-license-update-via-microsoft-365-admin-center"></a>オプション 2: Microsoft 365 管理センターを使用したユーザー ライセンスの一括更新

複数のユーザーのライセンスを一括で更新するには、Microsoft 365 管理センターを使用できます。 選択したユーザーは、同じライセンス プランの割り当てを持つことになります。

1. [admin.microsoft.com](https://admin.microsoft.com/) に移動し、テナント管理者の資格情報でサインインします。
1. **[ユーザー****アクティブ ユーザー]** >  に移動し、目的のすべてのユーザーを選択します。  
1. リスト ツール バーの [ **製品ライセンスの管理** ] を選択します。
1. **[これらのユーザーのライセンスをどうしますか?** ] プロンプトで、[**置換: 既存のライセンスの割り当て解除と新しいライセンスの割り当て**] オプションを選択します。
    > [!IMPORTANT]
    > **[置換]** オプションを選択すると、選択したユーザーの既存のすべてのライセンスが削除されます。  その結果、Microsoft 365 Business Premiumなど、使用中の他のライセンスも含め、ユーザーに対して目的のライセンス状態を選択する必要があります。
    >
    > また、選択したユーザーの基本ライセンス構成が異なる場合は、選択したライセンスで上書きされ、Microsoft 365 の他の領域に影響を与える可能性があります。
    >
    > 混合ライセンス設定のテナントの場合は、 [PowerShell スクリプトで一括更新オプションを](#option-3-bulk-user-license-update-using-a-powershell-script)使用することをお勧めします。
1. [ **ライセンスとアプリ** ] 画面で、Business Voice ライセンスの選択を解除します。
    > [!IMPORTANT]
    > 変更をまだ保存しないでください。 新しいライセンスを追加せずに変更を保存すると、選択したユーザーのアカウントはプロビジョニング解除され、電話番号は割り当て解除されます。
1. Business Voice の選択を解除した後、新しい Teams Phone および Audio Conferencing ライセンスを確認します。
1. これで、[変更の保存] を選択して、変更を安全 **に保存** できます。
  ユーザーのライセンスは更新され、サービスの可用性には影響しません。

# <a name="option-3-bulk-users-via-powershell"></a>[オプション 3: PowerShell を使用した一括ユーザー](#tab/powershell)

### <a name="option-3-bulk-user-license-update-using-a-powershell-script"></a>オプション 3: PowerShell スクリプトを使用したユーザー ライセンスの一括更新

PowerShell スクリプトを使用して Business Voice ライセンス プランを置き換えるのは、ほとんどのシナリオで効率的なソリューションです。  

このメソッドを使用するには、次の一般的な手順に従います。

1. 現在の Business Voice ライセンスのテナント固有のライセンス プラン識別子を取得します。
1. 新しい Teams Phone および Audio Conferencing ライセンス プランのテナント固有の識別子を取得します。
1. 新しいライセンス プランに、現在の Business Voice ライセンスと同じサービス プランがあるかどうかを検証します。
1. Business Voice のライセンスを持つテナント ユーザーを検索します (または、必要に応じて、フィルターを含めてユーザーのサブセットを選択するようにスクリプトを変更します)。
1. Teams Phone と電話会議のプランを使用してユーザーのライセンス構成を更新します。

> [!IMPORTANT]
> 提供されるスクリプトはコード サンプルです。 スクリプトをそのままコピーし、特定の環境のテスト、検証、カスタマイズを行わずに運用テナントで実行しないでください。

### <a name="how-to-bulk-update-licenses-using-powershell"></a>PowerShell を使用してライセンスを一括更新する方法

1. AzureAD PowerShell モジュールをインストールしてインポートします。

    ```powershell
    Install-Module AzureAD
    Import-Module AzureAD
    ```

1. Microsoft 365 テナントに接続し、テナント管理者の資格情報を指定します。

    ```powershell
    Connect-AzureAD
    ```

1. テナント内のすべてのライセンス パッケージを一覧表示するには、次のコマンドレットを使用します。

    ```powershell
    Get-AzureADSubscribedSku
    ```

1. 次の表を使用して、置き換える Business Voice アドオン ライセンス プランを特定します。

    | SKU コード | ライセンスの種類 |
    | -------- | ------------ |
    | BUSINESS_VOICE_MED | 通話プランを使用した Business Voice - カナダ |
    | BUSINESS_VOICE | 通話プランを使用したビジネス ボイス - UK |
    | BUSINESS_VOICE_MED2_TELCO | 通話プランを使用したビジネス 音声 - 米国 |
    | BUSINESS_VOICE_DIRECTROUTING | 通話プランのないビジネス音声 |
    | BUSINESS_VOICE_DIRECTROUTING_MED | 通話プランのないビジネス 音声 - 米国 |

    > [!NOTE]
    > このドキュメントで説明するスクリプトは、テナントに 1 つの SKU Code for Business Voice があることを前提としています。  
    >
    > 複数の Business Voice SKU がある場合は、スクリプトを調整するか、SKU コードごとに複数回実行する必要があります。

1. という名前 `$skuSourceBV`の PowerShell 変数を作成します。
    1. ラベルをテナントの `SkuPartNumber` Business Voice SKU Code に置き換えてください。
    1. この例では、SKU コードを `BUSINESS_VOICE_MED2_TELCO` 使用しています。

    ```powershell
    $skuSourceBV = Get-AzureADSubscribedSku  | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
    ```

1. 次の表を使用して、新しい Teams Phone および Audio Conferencing ライセンス SKU コードを識別します。

    | SKU コード | ライセンスの種類 |
    | -------- | ------------ |
    | MCOTEAMS_ESSENTIALS | 通話プランが設定された Teams 電話 |
    | MCOEV | Teams 電話スタンダード (通話プランなし) |
    | MCOMEETADV | 電話会議 |
    | Microsoft_Teams_Audio_Conferencing_select_dial_out | ダイヤルアウトを選択Microsoft Teams 電話会議 |

1. 一意の Teams Phone および電話会議 SKU コードを格納する PowerShell 変数を作成します。
    1. ラベルを `SkuPartNumber` 、テナントで使用できる SKU コードに置き換えてください。
    1. この例では、SKU コードと `MCOMEETADV` SKU コードを`MCOTEAM_ESSENTIALS`使用しています。

        ```powershell
        $skuTargetTPCP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
        $skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"} 
        ```

1. このスクリプトを実行して、ソース SKU から一意のオブジェクトに必要な Service Plan データを収集します。

     ```powershell
     $servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
    $servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
    $servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}
    ```

1. 次に進む前に、ソース SKU (Business Voice) とターゲット SKU (Teams Phone と Audio Conferencing) に同じサービス プランが含まれているかどうかを検証します。
    1. 不一致によりライセンスの変更がトリガーされ、ユーザーの音声および電話会議サービスが中断される可能性があります。
    2. ソース SKU 内のすべてのサービス プランが同じターゲット サービス プランに置き換えられるかどうかを検証する変数を作成します。

        ```powershell
        $validated_TP = $false
        $validated_AC = $false
        $validated_CP = $false
        ```

    3. ソースの Business Voice ライセンスに通話プランが含まれていない場合は、確認しないでください。

        ```powershell
        if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }
        ```

    4. ソース SKU 内のすべてのサービス プランに、ターゲット SKU に一致するサービス プランがあるかどうかを確認します。

        ```powershell
        For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) {
        if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
        if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
        if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
        }
        ```

    5. ターゲット SKU に不足しているサービス プランがある場合は、ユーザーのサービスの可用性を中断する可能性があり、スクリプトの処理を停止する必要があります。

        ```powershell
        if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit }
        if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit }
        if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit }
        ```

1. すべてが適切に見える場合は、PowerShell オブジェクトを準備して、ユーザー オブジェクトに対して更新操作を実行します。 このためにオブジェクトを `AssignedLicenses` 使用します。

    ```powershell
    $LicenseAddTPCP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddTPCP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTPCP.SkuPartNumber -EQ).SkuID
    $LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
    
    $LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
    $LicensesToUpdate.AddLicenses += ($LicenseAddTPCP)
    $LicensesToUpdate.AddLicenses += ($LicenseAddAC)
    $LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID
    ```

1. 次に、Business Voice ライセンスが割り当てられているユーザーの一覧を取得し、.`$usersLicensedOldSKU`

    ```powershell
    $usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
    
    Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }
    ```

1. 次に、新しいユーザーの一覧を使用して、更新アクティビティを実行して Business Voice ライセンスを削除し、前に作成したオブジェクトを使用して ``$LicensesToUpdate`` Teams Phone ライセンスと電話会議ライセンスを追加します。

    ```powershell
    $usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
    ```

> [!NOTE]
> Business Voice を置き換えるための十分な Teams Phone または電話会議ライセンスがない場合は、ライセンスのプールが枯渇するとすぐに、ユーザー割り当て中に **SKU guid を使用したサブスクリプションに使用可能なライセンス** がないというエラーが表示されます。

### <a name="full-script"></a>完全なスクリプト

```powershell
#Install the AzureAD module when required
Install-Module AzureAD
#Import the AzureAD module so you can use the commandlets
Import-Module AzureAD

#Connect to your tenant
Connect-AzureAD

#When necessary, uncomment and use this commandlet to list all the licenses in the tenant and identify which license packages are required
#Get-AzureADSubscribedSku

##Replace the SKU codes below to match your desired scenario
$skuSourceBV = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
$skuTargetTP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
$skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"}

##Replace the SKU codes below to match your desired scenario
$servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
$servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
$servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}

##Create variables to validate if all Service Plans in the source SKU will be replaced with the same target service plan
$validated_TP = $false
$validated_AC = $false
$validated_CP = $false

##If source Business Voice has no Calling Plan included, do not check
if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }

##Verify if all service plans in source SKU have a matching service plan in target SKU
For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) { 
    if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
    if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
    if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
}

##If there's a missing service plan in the target sku, we might impact service availability for a user and therefore stop processing
if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit } 
if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit } 
if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit } 


##Prepare variables and update
$LicenseAddTP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddTP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTP.SkuPartNumber -EQ).SkuID
$LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
$LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToUpdate.AddLicenses += ($LicenseAddTP)
$LicensesToUpdate.AddLicenses += ($LicenseAddAC)
$LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID

$usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }

$usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
```

# <a name="option-4-bulk-users-with-azure-group-based-licensing"></a>[オプション 4: Azure グループ ベースのライセンスを持つ一括ユーザー](#tab/azure-licensing)

### <a name="option-4-bulk-user-license-update-using-azure-group-based-licensing"></a>オプション 4: Azure グループ ベースのライセンスを使用したユーザー ライセンスの一括更新

Azure グループ ベースのライセンス管理を使用すると、サブスクリプションとサービス プランをグループに割り当てることができます。

このメソッドにより、次のことが保証されます。

- ライセンスは、グループのすべてのメンバーに割り当てられます。
- グループに参加する新しいメンバー全員に、適切なライセンスが割り当てられます。
- メンバーがグループから削除されると、それらのライセンスも削除されます。

[グループ ベースのライセンスのライセンス要件を検証する必要があります](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。

> [!NOTE]
> この方法では、ライセンスの更新を 1 つの手順で処理する必要があります。
>
> Business Voice ライセンスが割り当てられている既存のグループの一覧をコンパイルし、最初に小規模なテスト ユーザー グループを選択し、ライセンス プランの割り当てを優先する新しいライセンス プランに置き換えることをお勧めします。

### <a name="how-to-bulk-update-licenses-using-group-based-licensing"></a>グループ ベースのライセンスを使用してライセンスを一括更新する方法

1. [portal.azure.com](https://portal.azure.com) に移動し、管理者資格情報でサインインします。
1. **Azure Active Directory** に移動し、左側のメニューで **[ライセンス**] を選択します。
1. どのグループに Business Voice ライセンスが割り当てられているかを確認するには、 **すべての製品** を選択し、Business Voice プランを選択します。
1. **[ライセンス グループ]** または [**ライセンスユーザー**] を選択します。 ライセンスされたグループの一覧は、右側のウィンドウに表示されます。
1. グループ名を選択して、グループの割り当ての詳細を開きます。
1. [ **割り当て]** を選択して、このグループに割り当てられているライセンスを変更します。
1. Business Voice を置き換えるために取得したライセンス プランの前にあるチェック ボックスをオンにします。
1. Microsoft 365 Business Voice ライセンス プランの前にあるチェック ボックスをオフにします。
1. **[保存]** を選択します。
1. グループ名を選択して、グループに戻ります。 **ライセンスの変更が保留中** であることを示すバナーが表示されます。
1. **[再処理**] を選択して、ライセンスの割り当てを強制的に更新します。

---

## <a name="validate-user-license-updates"></a>ユーザー ライセンスの更新を検証する

選択した方法を完了したら、ユーザー ライセンスが適切に更新されたかどうかを検証します。

1. [Microsoft 365 管理センター](https://admin.microsoft.com)に移動し、管理者資格情報でサインインします。
1. **[ユーザー** > **] アクティブ ユーザー** に移動し、テスト ユーザーを選択します。
1. ツール バーの [ **製品ライセンスの管理** ] を選択します。
1. [ **ライセンスとアプリ** ] 画面で、割り当てたライセンスを確認します。

対象となるすべてのユーザーに適切なライセンスが割り当てられている場合は、Teams Phone ライセンスと電話会議ライセンスへの Business Voice ライセンスの更新が完了しました。
