---
title: "電話会議プロバイダーとして Microsoft を割り当てる"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/23/2018
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
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
- Audio Conferencing
- Strat_SB_PSTN
description: "Microsoft Skype for Business のダイヤルイン会議プロバイダーを割り当てる方法について説明します。会議ブリッジします。"
ms.openlocfilehash: d6c0f4f3a8f903ff180785214d3a4e987321a5b3
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>電話会議プロバイダーとして Microsoft を割り当てる

電話会議プロバイダーは*会議ブリッジ*を提供します。会議ブリッジにダイヤルイン電話番号、ピン、作成した会議の会議 Id を提供します。Skype を潜在顧客のビジネスまたは Microsoft チーム会議やスケジュールを設定する人に電話会議プロバイダーを割り当てる必要があるだけです。
  
オーディオのプロバイダーとして**Microsoft**が一覧表示されていることができる場合は、ユーザーに**電話会議**のライセンスを割り当てる必要があります。
  
> [!NOTE]
> サードパーティ電話会議プロバイダーに登録していない人に**電話会議**のライセンスを割り当てると、電話会議プロバイダーとして Microsoft が自動的に割り当てられます。必要な場合は、[サードパーティ電話会議プロバイダーとしての割り当て](assign-a-third-party-as-the-audio-conferencing-provider.md)をお試しください。
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>電話会議プロバイダーとして Microsoft を割り当てる

### <a name="using-the-skype-for-business-admin-center"></a>Business 管理センターの Skype を使用します。

1. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
    > [!NOTE]
    > プロバイダーは、別のプロバイダーから**Microsoft**に変更は、(会議 ID、有料フリー ダイヤルの番号) のユーザーの電話会議の情報が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。 
  
2. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **ユーザー**の場合は、し、使用可能なユーザーの一覧からユーザーを選択します。
    
3. 操作ウィンドウで、[**編集**] をクリックします。
    
4. [**プロバイダー名**] で、ユーザーの [プロパティ] ページには、ドロップダウン リストで**Microsoft**を選択します。
    
    > [!NOTE]
    > 電話会議プロバイダーとして Microsoft を使用して複数の電話番号があるため、**有料電話番号が既定**のドロップダウン リストを使用してユーザーの既定のオーディオ数を選択することができます。
  
5. {[**保存**] をクリックします。}
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>少数のユーザーの Windows PowerShell スクリプトを使用します。

時間を節約し、自動化したり、少数のユーザーの電話会議プロバイダーとして Microsoft を設定するのに次の PowerShell スクリプトを使用することができます。

> [!NOTE]
> プロバイダーは、別のプロバイダーから**Microsoft**に変更は、(会議 ID、有料フリー ダイヤルの番号) のユーザーの電話会議の情報が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。 
  
次のスクリプトの 1 つ以上を PowerShell スクリプト ファイルとして保存し、それを実行できます。
  
少数のユーザーに Microsoft に、プロバイダーを変更するには、[有効にする CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx)を使用できます。
  
**例 1:**このスクリプトを実行するには、更新するユーザーのリストを提供します。
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
**例 2:**このスクリプトを実行するには、各ユーザーのメール アドレス (alias) を含む .csv ファイルを更新することを提供します。  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>多数のユーザーの Windows PowerShell スクリプトを使用します。
時間を節約し、自動化したり、次の PowerShell スクリプトを使用して多数のユーザーの電話会議プロバイダーとして Microsoft を設定することができます。

プロバイダーは、別のプロバイダーから**Microsoft**に変更は、(会議 ID、有料フリー ダイヤルの番号) のユーザーの電話会議の情報が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。 
  
次のスクリプトの 1 つ以上を PowerShell スクリプト ファイルとして保存し、それを実行できます。

**例 1:**この例でこのスクリプト Intercall から電話会議プロバイダー (または別のプロバイダー) を変更するのに使える**Microsoft**大きい数値のユーザーの組織でします。
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  スクリプトを示します。

  ```
  <#
  .SYNOPSIS

  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .DESCRIPTION
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .EXAMPLE
  
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ./Script.ps1 -ACPProviderName ""Intercall""
  #>
  param (
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
   [string]$CsvFile,
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
   [string]$UserList,
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  [string]$ACPProviderName
  )
  if ($CsvFile)
  {
  if(!(Test-Path $CsvFile))
  {
  Write-Error "File does not exist."
  Exit
   }
  $users = Get-Content $CsvFile
  }
  if ($UserList)
  {
  $users = $UserList.Split(",")
  }
  if ($ACPProviderName)
  {
  $supportedACPProviders = Get-csAudioConferencingProvider
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  if ($providerNameMatch -eq $null)
  {
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  $supportedACPProviders      | %{$_.Identity}
  return
  }
  $allUsersInTenant = Get-csOnlineUser
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  }
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.count
  foreach ($user in $users)
  {
  if ($CsvFile -or $UserList)
  {
  try
  {
  $adUser = Get-csOnlineUser -Identity $user
  }
  catch
  {
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  Continue
  }
  }
  else
  {
  $adUser = $user
  }
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  {
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  {
  try
  {
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  Write-Host "The provider of $user has changed to Microsoft."
  $enableUser
  }
  catch
  {
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  continue;
  }
  }
   else
  {
  Write-Warning "The provider of $user is already set to Microsoft."
  }
  }
  else
              {
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  }
  }
  ```
詳細については、Windows PowerShell を使用して、[共通の Skype for Business Online の管理タスクを実行する Windows PowerShell を使用する](https://go.microsoft.com/fwlink/?LinkId=525038)を参照してください。
  
## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- ユーザーは、電話会議プロバイダーの 1 つだけ割り当てることができます。
    
- いつでも Microsoft からサードパーティ プロバイダーに電話会議プロバイダーを変更できます。詳細については、[電話会議プロバイダーとしてサードパーティの割り当て](assign-a-third-party-as-the-audio-conferencing-provider.md)を参照してください。
    
- 自分の組織では、自分の電話会議プロバイダーとして Microsoft を使用している一部のユーザーと他のユーザーをサードパーティ プロバイダーを使用していることができます。セットアップし、管理をより複雑になります。
    
## <a name="related-topics"></a>関連トピック

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)
  
[Skype for Business Online をセットアップします。](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)