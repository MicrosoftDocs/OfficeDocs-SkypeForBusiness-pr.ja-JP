---
title: "ダイヤル プランを作成および管理する"
ms.author: tonysmit
author: tonysmit
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
description: "Learn how to create calling dial plans (PSTN Calling dial plans) in Office 365 and how to manage them. "
---

# ダイヤル プランを作成および管理する

組織のためにダイヤル プランを作成し、通話ルーティングのために作成される必要があるすべての正規化ルールを理解した後に、ダイヤル プランを作成して設定変更を行うために Windows PowerShell を使用する必要があります。
  
> [!NOTE]
> Skype for Business 管理センターは、ダイヤル プランを作成および管理するために使用できません。 
  
## リモート PowerShell の検証と開始

 **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
  
1. バージョン 3.0 以降を実行していることを確認するには [ **スタート**] メニューから [ **Windows PowerShell**] を選びます。
    
2. [ **Windows PowerShell**] ウィンドウに「 _Get-Host_」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。
  
 **Windows PowerShell セッションを開始する**
  
1. [ **スタート**] メニューで [ **Windows PowerShell**] を選びます。
    
2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
    > [!NOTE]
    > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Windows PowerShell の起動の詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」または「[Windows PowerShell を使用した Lync Online への接続](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)」を参照してください。
  
## ダイヤル プランの作成と管理

テナント ダイヤル プランを作成および管理するために単一のコマンドレットまたは PowerShell スクリプトのいずれかを使用できます。
  
### 単一のコマンドレットの使用

- ダイヤル プランを新規作成するには、次を実行します。
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    その他の例とパラメーターについては、「[New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx)」をご覧ください。
    
- 既存のダイヤル プランの設定を変更するには、次を実行します。
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    その他の例とパラメータについては、「[Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx)」をご覧ください。
    
- ユーザーをダイヤル プランに追加するには、次を実行します。
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    その他の例とパラメータについては、「[Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx)」をご覧ください。
    
- ダイヤル プランの設定を表示するには、次を実行します。
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    その他の例とパラメータについては、「[Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx)」をご覧ください。
    
- ダイヤル プランを削除するには、次を実行します。
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    その他の例とパラメータについては、「[Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx)」をご覧ください。
    
- 有効なダイヤル プランの設定を表示するには、次を実行します。
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    その他の例とパラメータについては、「[Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx)」をご覧ください。
    
- ダイヤル プランの有効な設定をテストするには、次を実行します。
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    その他の例とパラメータについては、「[Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx)」をご覧ください。
    
### PowerShell スクリプトの使用

これを実行して、最初にテナント ダイヤル プランを削除することなく、テナント ダイヤル プランに関連付けられた正規化ルールを削除します。
  
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
```

```
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
```

```
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```

これを実行して、次の正規化ルールを RedmondDialPlan という名前の既存のテナント ダイヤル プランに追加します。
  
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```

これを実行して、次の正規化ルールを RedmondDialPlan という名前の既存のテナント ダイヤル プランから削除します。
  
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
```

```
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

既存の正規化ルールを調べて、どれを削除するかを決定し、そのインデックスを使用して削除するときには、次を実行します。正規化ルールの配列は、インデックス 0 で開始します。インデックス 1 である、3 桁の正規化ルールを削除する必要があります。
  
```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
```

```
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
```

```
$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

これを実行して、RedmondDialPlan テナント ダイヤル プランが付与されているすべてのユーザーを見つけます。
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

これらを実行して、OPDP1 という名前の既存のオンプレミス ダイヤル プランを組織のテナント ダイヤル プランとして追加します。まずオンプレミス ダイヤル プランを xml ファイルに保存してから、それを使用して新しいテナント ダイヤル プランを作成する必要があります。
  
これを実行して、オンプレミス ダイヤル プランを xml ファイルに保存します。
  
```
$DPName = "OPDP1"
```

```
$DPFileName = "dialplan.xml"
```

```
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

これを実行して、新しいテナント ダイヤル プランを作成します。
  
```
$DPFileName = "dialplan.xml"
```

```
$DP = Import-Clixml $DPFileName
```

```
$NormRules = @()
```

```
ForEach($nr in $dp.NormalizationRules)
```

```
{
```

```
 $id1 = "Global/" +$nr.Name
```

```
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
```

```
$NormRules += $nr2
```

```
}
```

```
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```

## Windows PowerShell の詳細情報

- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    

