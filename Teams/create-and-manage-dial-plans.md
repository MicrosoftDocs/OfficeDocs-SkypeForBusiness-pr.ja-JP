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
description: Microsoft Teams 管理センターまたは Windows PowerShell を使用して、ダイヤルプラン (PSTN 通話ダイヤルプラン) を作成および管理する方法について説明します。
ms.openlocfilehash: 966ac2e21d3bc57dd32a0b2732e0be285b9fdf0d
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691343"
---
# <a name="create-and-manage-dial-plans"></a>ダイヤル プランを作成および管理する

組織のダイヤルプランを計画し、通話ルーティング用に作成する必要があるすべての正規化ルールを把握したら、ダイヤルプランを作成することができます。 Microsoft Teams 管理センターまたは Windows PowerShell を使用して、ダイヤルプランを作成し、管理することができます。  

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

### <a name="create-a-dial-plan"></a>ダイヤルプランを作成する

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **ダイヤルプラン**] に移動します。
2. [**追加**] をクリックして、ダイヤルプランの名前と説明を入力します。
    ![ダイヤルプランを作成するための [追加] ページを示すスクリーンショット](media/create-dial-plan.png)
3. [**ダイヤルプランの詳細**] で、ユーザーが1つまたは複数の追加の先頭の数字 (9 など) をダイヤルする必要がある場合は、外部ダイヤルのプレフィックスを指定します。 その手順は次のとおりです。
    1. [外線**発信**番号] ボックスに、外線発信番号を入力します。 プレフィックスは、最大4文字 (#、*、0-9) にすることができます。
    2. 最適化された**デバイスダイヤル**をオンにします。 外線発信番号を指定する場合は、組織外に通話を発信できるようにプレフィックスを適用するには、この設定を有効にする必要もあります。
4. [**正規化ルール**] で、ダイヤルプランに1つまたは複数の[正規化ルール](what-are-dial-plans.md#normalization-rules)を構成して関連付けます。 各ダイヤルプランには、少なくとも1つの正規化ルールが関連付けられている必要があります。  この操作を行うには、次の操作のいずれか、または複数の操作を行います。
    - 新しい正規化ルールを作成してダイヤルプランに関連付けるには、[**追加**] をクリックして、ルールを定義します。
    - 既にダイヤルプランに関連付けられている正規化ルールを編集するには、ルール名の左側をクリックしてルールを選択し、[**編集**] をクリックします。 必要な変更を加えて、[**保存**] をクリックします。
    - ダイヤルプランから正規化ルールを削除するには、ルール名の左側をクリックしてルールを選択し、[**削除**] をクリックします。
5. 目的の順序で正規化ルールを配置します。 一覧のルールの位置を変更するには、[**上へ移動**] または [**下**へ移動] をクリックします。

    > [!NOTE]
    > チームは正規化ルールの一覧を上から下に移動し、ダイヤルされた番号に一致する最初のルールを使用します。 ダイヤルプランを設定して、ダイヤルした番号が複数の正規化ルールと一致するようにする場合は、制限の少ない制限を超えて、より制限されたルールが並べ替えられるようにします。

6. **[保存]** をクリックします。
7. ダイヤルプランをテストするには、[**ダイヤルプランのテスト**] で電話番号を入力し、[**テスト**] をクリックします。

### <a name="edit-a-dial-plan"></a>ダイヤルプランを編集する

1. Microsoft Teams 管理センターの左のナビゲーションで、[**ボイス**  >  **ダイヤルプラン**] に移動します。
2. ダイヤルプラン名の左側をクリックして、[**編集**] をクリックして、ダイヤルプランを選択します。
3. 必要な変更を加えて、[**保存**] をクリックします。

### <a name="add-users-to-a-dial-plan"></a>ダイヤルプランにユーザーを追加する

1. Microsoft Teams 管理センターの左側のナビゲーションで、[**ユーザー**] に移動します。
2. 表示名をクリックしてユーザーを選びます。
3. [**ポリシー** ] タブを選択します。
4. [割り当てられたポリシー] の右にある [**編集**] をクリックします。
5. [ **Dial plan** ] ドロップダウンメニューで、ユーザーに割り当てるダイヤルプランを選択し、[**適用**] をクリックします。

## <a name="using-powershell"></a>PowerShell を使用する場合
  
### <a name="verify-and-start-remote-powershell"></a>リモート PowerShell を確認して開始する

 **Windows PowerShell バージョン3.0 以降を実行していることを確認する**
  
1. バージョン3.0 以降を実行していることを確認**Start Menu**するには、「  >  **Windows PowerShell**を開始する」をご覧ください。
    
2. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
    
3. バージョン3.0 以降を使っていない場合は、Windows PowerShell に更新プログラムをダウンロードしてインストールします。 Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。 メッセージが表示されたら、コンピューターを再起動します。
    
4. また、skype for business online に接続するリモート Windows PowerShell セッションを作成できるようにする、Skype for Business Online 用の Windows PowerShell モジュールをインストールする必要もあります。 このモジュールは、64ビットのコンピューターでのみサポートされていますが、 [Skype For Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)でダウンロードできます。 メッセージが表示されたら、コンピューターを再起動します。
    
詳細については、「[単一の Windows PowerShell ウィンドウですべての Microsoft 365 または Office 365 サービスに接続する](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)」を参照してください。
  
 **Windows PowerShell セッションを開始する**
  
1. [ **Start**  >  **Windows PowerShell**を起動します] をクリックします。
    
2. **Windows PowerShell**ウィンドウで、次を実行して Microsoft 365 または Office 365 に接続します。
    
    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a>ダイヤルプランを作成して管理する

テナント ダイヤル プランを作成および管理するために単一のコマンドレットまたは PowerShell スクリプトのいずれかを使用できます。
  
#### <a name="using-single-cmdlets"></a>単一のコマンドレットの使用

- ダイヤル プランを新規作成するには、次を実行します。
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    その他の例とパラメーターについては、「[New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan)」をご覧ください。
    
- 既存のダイヤルプランの設定を編集するには、次を実行します。
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    その他の例とパラメータについては、「[Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan)」をご覧ください。
    
- ユーザーをダイヤル プランに追加するには、次を実行します。
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    その他の例とパラメータについては、「[Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan)」をご覧ください。
    
- ダイヤル プランの設定を表示するには、次を実行します。
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    その他の例とパラメータについては、「[Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps)」をご覧ください。
    
- ダイヤル プランを削除するには、次を実行します。
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    その他の例とパラメータについては、「[Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)」をご覧ください。
    
- 有効なダイヤル プランの設定を表示するには、次を実行します。
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    その他の例とパラメータについては、「[Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan)」をご覧ください。
    
- ダイヤル プランの有効な設定をテストするには、次を実行します。
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    その他の例とパラメータについては、「[Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)」をご覧ください。
    
#### <a name="using-a-powershell-script"></a>PowerShell スクリプトの使用

これを実行して、最初にテナントダイヤルプランを削除することなく、テナントダイヤルプランに関連付けられている正規化ルールを削除します。
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

これを実行して、HostingProvider の sipfed.online.lync.com を持つすべてのユーザーから割り当てられている TenantDialPlan を削除します。
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
    
## <a name="related-topics"></a>関連項目

- [ダイヤル プランについて](what-are-dial-plans.md)
- [電話番号の移行に関するよくある質問](transferring-phone-numbers-common-questions.md)
- [通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Teams での PowerShell の概要](teams-powershell-overview.md)
