---
title: "Microsoft を電話会議プロバイダーとして割り当てる"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/23/2018
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- Strat_SB_PSTN
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge.
ms.openlocfilehash: 0193743f9dd2ed6486d93d55c881f3e582e4eb04
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Microsoft を電話会議プロバイダーとして割り当てる

オーディオ会議プロバイダーでは、*テレビ会議サービス*を提供します。 会議ブリッジでは、ダイヤルインの電話番号、Pin、および作成された会議の会議 Id を提供します。 必要なのは、電話会議プロバイダーを Skype for Business 会議または Microsoft Teams 会議をスケジュールまたは開催しようとしている人に割り当てることだけです。
  
**マイクロソフト**は、オーディオのプロバイダーとして一覧表示されていることができる場合は、**オーディオ会議**のライセンスをユーザーに割り当てる必要があります。
  
> [!NOTE]
> **オーディオ会議**のライセンスを割り当てるには、サード ・ パーティ製のオーディオ会議プロバイダーをインストールしていない人に、オーディオ会議プロバイダーとしてマイクロソフトが自動的に割り当てられます。 必要な場合は[、サードパーティのオーディオ会議プロバイダーとしての割り当て](assign-a-third-party-as-the-audio-conferencing-provider.md)を実行できます。
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Microsoft を電話会議プロバイダーとして割り当てる

### <a name="using-the-skype-for-business-admin-center"></a>Skype for Business 管理センターを使用する

1. Go to the **Office 365 admin center** > **Skype for Business**.
    
    > [!NOTE]
    > プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。 
  
2. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **のユーザー**、および利用可能なユーザーの一覧からユーザーを選択します。
    
3. 操作ウィンドウで、[ **編集**] をクリックします。
    
4. [**プロバイダー名**] で、ユーザーの [プロパティ] ページのドロップダウン ボックスの一覧で**Microsoft**を選択します。
    
    > [!NOTE]
    > オーディオ会議プロバイダーとして、Microsoft を使用している複数の電話番号があるため、ユーザーの既定の音声番号を選択するのには、**有料電話番号が既定**のドロップ ダウン リストを使用できます。
  
5. [ **保存**] をクリックします。
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>少数のユーザーのために Windows PowerShell スクリプトを使用する

時間を節約して自動化するために、次の PowerShell スクリプトを使用して、少数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。

> [!NOTE]
> プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。 
  
次の 1 つまたは複数のスクリプトを PowerShell スクリプト ファイルとして保存して実行することができます。
  
マイクロソフトのユーザー数が少ないためにプロバイダーを変更するには、[有効にする CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx)を使用できます。
  
**例 1:** 更新したいユーザーのリストを指定して、このスクリプトを実行できます。
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
**例 2:** 更新したい各ユーザーの電子メール アドレス (エイリアス) を含む .csv ファイルを指定して、このスクリプトを実行できます。  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>多数のユーザーのために Windows PowerShell スクリプトを使用する
時間を節約して自動化するために、次の PowerShell スクリプトを使用して、多数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。

プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。 
  
次の 1 つまたは複数のスクリプトを PowerShell スクリプト ファイルとして保存して実行することができます。

**例 1:** この例では、このスクリプトを使用して、組織内の多数のユーザーのために電話会議プロバイダーを Intercall (またはプロバイダー) から **Microsoft** に変更することができます。
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  スクリプトを以下に示します。

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
Windows PowerShell の使い方の詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。
  
## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- 1 人のユーザーに割り当てられるのは 1 つの電話会議プロバイダーのみです。
    
- いつでも電話会議プロバイダーをマイクロソフトからサードパーティのプロバイダーに変更することができます。詳細については、「[サードパーティを電話会議プロバイダーとして割り当てる](assign-a-third-party-as-the-audio-conferencing-provider.md)」をご覧ください。
    
- 組織内で、電話会議プロバイダーとして Microsoft を使用している人とサードパーティを使用している人が混在している場合があります。しかし、このような場合、設定と管理がより複雑になります。
    
## <a name="related-topics"></a>See also

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

