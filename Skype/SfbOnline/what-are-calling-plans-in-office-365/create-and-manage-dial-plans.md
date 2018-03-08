---
title: "作成してダイヤル プランを管理します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Office 365 で通話ダイヤル プラン (PSTN 通話ダイヤル プラン) を作成する方法とそれを管理する方法について説明します。 "
ms.openlocfilehash: 6bef6ce242158e5bddf812a5c8fc03d52e4288e5
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="create-and-manage-dial-plans"></a>作成してダイヤル プランを管理します。

組織のダイヤル プランを計画し、すべての通話のルーティングに作成する必要がある正規化ルールをした後は、Windows PowerShell を使用して、ダイヤル プランを作成し、設定を変更する必要があります。
  
> [!NOTE]
> Skype for Business 管理センターを作成して、ダイヤル プランの管理については使用できません。 
  
## <a name="verifying-and-starting-remote-powershell"></a>確認し、リモート PowerShell を開始します。

 **3.0 以降のバージョンの Windows PowerShell が実行していることを確認します。**
  
1. 3.0 以降のバージョンが実行していることを確認する: **[スタート] メニュー** > **Windows PowerShell**します。
    
2. **Windows PowerShell**のウィンドウで_ホストの取得_を入力して、バージョンを確認してください。
    
3. バージョン 3.0 以降をお持ちでない場合は、ダウンロードして、Windows PowerShell への更新プログラムをインストールする必要があります。[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)をダウンロードして 4.0 への Windows PowerShell を更新するを参照してください。表示されたら、お使いのコンピューターを再起動します。
    
4. Skype for Business Online できるようにする Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成するのには、Windows PowerShell モジュールをインストールする必要もします。このモジュールでは、64 ビット版コンピューターにのみサポートされているが、 [Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)では、Microsoft ダウンロード センターからダウンロードできます。求められた場合は、お使いのコンピューターを再起動します。
    
さらに詳しく調べ必要がある場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスへの接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)を参照してください。
  
 **Windows PowerShell セッションを開始します。**
  
1. **[スタート] メニュー**から > **Windows PowerShell**します。
    
2. **Windows PowerShell**ウィンドウで、実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online の Windows PowerShell モジュールに使用する**インポート モジュール**の最初のレコード] コマンドの実行にのみがあります。
  
> 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

詳細については、Windows PowerShell を開始する場合は、[単一の Windows PowerShell ウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」または「 [Skype for Business Online Windows PowerShell を使用してへ接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。
  
## <a name="creating-and-managing-your-dial-plans"></a>作成と、ダイヤル プランの管理

単一のコマンドレットまたは PowerShell スクリプトを使用して、作成ダイヤル プランのテナントを管理することができますか。
  
### <a name="using-single-cmdlets"></a>1 つのコマンドレットを使用します。

- 新しいダイヤル プランを作成するには、次のように実行します。
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    その他の例とパラメーターを使用して、[新しい CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx)を参照してください。
    
- 既存のダイヤル プランに設定を変更するには、次のコマンドを実行します。
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    その他の例とパラメーターを使用して、[セット CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx)を参照してください。
    
- ダイヤル プランにユーザーを追加するには、次のコマンドを実行します。
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    その他の例とパラメーターを使用して、[許可を付与する CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx)を参照してください。
    
- 設定を表示するには、ダイヤル プランで、次のコマンドを実行します。
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    その他の例とパラメーターを使用して、 [Get CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx)を参照してください。
    
- ダイヤル プランを削除するには、次のコマンドを実行します。
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    その他の例とパラメーターを使用して、[削除 CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx)を参照してください。
    
- 効果的なダイヤル プランの設定を表示するには、次のコマンドを実行します。
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    その他の例とパラメーターを使用して、 [Get CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx)を参照してください。
    
- ダイヤル プランの有効な設定をテストするには、次のように実行します。
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    その他の例とパラメーターを使用して、[テスト CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx)を参照してください。
    
### <a name="using-a-powershell-script"></a>PowerShell スクリプトを使用します。

実行テナントに関連付けられている正規化ルールを削除するダイヤル プランしなくても、テナント ダイヤル プランを最初に削除します。
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
既存のテナント ダイヤル プラン RedmondDialPlan という名前に、次の正規化ルールを追加するときに実行します。
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
RedmondDialPlan という名前の既存のテナント ダイヤル プランから、次の正規化ルールを削除するのにはこれを実行します。
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

既存の正規化ルールを調べることを判断するには、削除して、削除するのには、インデックスを使用する場合は、次を実行します。正規化ルールの配列インデックス 0 から始まります。3 桁の正規化ルール、ように 1 のインデックスを削除するたいと思います。
  
```
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

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

ダイヤル プランを RedmondDialPlan テナントが付与されているすべてのユーザーの検索を実行します。
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

既存のオンプレミス ダイヤル プラン OPDP1 テナントのダイヤル プランを組織の名前を追加するのには次を実行します。まず、内部設置型に保存ダイヤル プラン] .xml ファイルにして、新しいテナント ダイヤル プランを作成する必要があります。
  
内部設置型のダイヤル プランを .xml ファイルに保存するときに実行します。
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

新しいテナント ダイヤル プランを作成するのにはこれを実行します。
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a>Windows Powershell の詳細を知りたいとしていますか。

- Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック
[電話番号のよく寄せられる質問を転送します。](transferring-phone-numbers-common-questions.md)

[さまざまなプランの呼び出し用の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理します。](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[緊急の呼び出し元の条項および条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急発信免責事項のラベル](https://go.microsoft.com/fwlink/?LinkID=692099)

