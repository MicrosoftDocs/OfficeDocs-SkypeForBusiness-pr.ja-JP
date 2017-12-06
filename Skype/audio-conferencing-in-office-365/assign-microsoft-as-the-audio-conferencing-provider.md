---
title: "Microsoft を電話会議プロバイダーとして割り当てる"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
description: "Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge."
---

# Microsoft を電話会議プロバイダーとして割り当てる

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「[免責事項](d935a90d-ea61-433d-a820-b400ed9c1f5d.md#MT_Footer)」をお読みください。この記事の英語版を参照するには、[ここ](https://support.office.com/en-us/article/d935a90d-ea61-433d-a820-b400ed9c1f5d)をクリックしてください。 
  
電話会議プロバイダーは *会議ブリッジ*  を提供します。会議ブリッジにダイヤルイン電話番号、ピン、作成した会議の会議 Id を提供します。スケジュールの設定またはSkype for Businessまたは Microsoft チーム会議を進行するユーザーに電話会議プロバイダーを割り当てる必要があるだけです。
  
オーディオのプロバイダーとして **Microsoft**が一覧表示されていることができる場合は、ユーザーに **電話会議**のライセンスを割り当てる必要があります。
  
> [!NOTE]
> サードパーティ電話会議プロバイダーに登録していない人に **電話会議**のライセンスを割り当てると、電話会議プロバイダーとして Microsoft が自動的に割り当てられます。必要に応じて[サードパーティを電話会議プロバイダーとして割り当てる](assign-a-third-party-as-the-audio-conferencing-provider.md)できます。 
  
## Microsoft を電話会議プロバイダーとして割り当てる

### Skype for Business 管理センターを使用する

1. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
    > [!NOTE]
    > プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。
  
2. [ **[Skype for Business 管理センター]**、左のナビゲーションで **電話会議**に移動 > **ユーザー**の場合は、し、使用可能なユーザーの一覧からユーザーを選択します。
    
3. 操作ウィンドウで、[ **編集**] をクリックします。
    
4. [ **プロバイダー名**] で、ユーザーの [プロパティ] ページには、ドロップダウン リストで **Microsoft**を選択します。
    
    > [!NOTE]
    > 電話会議プロバイダーとして Microsoft を使用して複数の電話番号があるため、 **有料電話番号が既定**のドロップダウン リストを使用してユーザーの既定のオーディオ数を選択することができます。 
  
5. [ **保存**] をクリックします。
    
### 少数のユーザーの Windows PowerShell スクリプトを使用します。

時間を節約して自動化するために、次の PowerShell スクリプトを使用して、少数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。
  
> [!NOTE]
> プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。
  
次の 1 つまたは複数のスクリプトを PowerShell スクリプト ファイルとして保存して実行することができます。
  
少数のユーザーのためにプロバイダーを Microsoft に変更するには、[Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) を使用できます。
  
> **例 1:** 更新したいユーザーのリストを指定して、このスクリプトを実行できます。
    
> 
  ```
  Script.ps1 -UserList <List of users>
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> **例 2:** 更新したい各ユーザーの電子メール アドレス (エイリアス) を含む .csv ファイルを指定して、このスクリプトを実行できます。
    
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

### 多数のユーザーのために Windows PowerShell スクリプトを使用する

時間を節約して自動化するために、次の PowerShell スクリプトを使用して、多数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。
  
> [!NOTE]
> プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。
  
次の 1 つまたは複数のスクリプトを PowerShell スクリプト ファイルとして保存して実行することができます。
  
> **例 1:** この例では、このスクリプトを使用して、組織内の多数のユーザーのために電話会議プロバイダーを Intercall (またはプロバイダー) から **Microsoft** に変更することができます。
    
> 
  ```
  Script.ps1 -ACPProviderName <Provider>
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName "Intercall"
  ```

    **スクリプトは次のとおりです。**
    
> 

> 
  ```
  <#
  ```

> 
  ```
  .SYNOPSIS

  ```

  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .DESCRIPTION
  ```

> 
  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .EXAMPLE
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName ""Intercall""
  ```

> 
  ```
  #>
  ```

> 
  ```
  param (
  ```

> 
  ```
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
  ```

> 
  ```
   [string]$CsvFile,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
  ```

> 
  ```
   [string]$UserList,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  ```

> 
  ```
  [string]$ACPProviderName
  ```

> 
  ```
  )
  ```

> 
  ```
  if ($CsvFile)
  ```

> 
  ```
  {
  ```

> 
  ```
  if(!(Test-Path $CsvFile))
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "File does not exist."
  ```

> 
  ```
  Exit
  ```

> 
  ```
   }
  ```

> 
  ```
  $users = Get-Content $CsvFile
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  $users = $UserList.Split(",")
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($ACPProviderName)
  ```

> 
  ```
  {
  ```

> 
  ```
  $supportedACPProviders = Get-csAudioConferencingProvider
  ```

> 
  ```
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  ```

> 
  ```
  if ($providerNameMatch -eq $null)
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  ```

> 
  ```
  $supportedACPProviders      | %{$_.Identity}
  ```

> 
  ```
  return
  ```

> 
  ```
  }
  ```

> 
  ```
  $allUsersInTenant = Get-csOnlineUser
  ```

> 
  ```
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  ```

> 
  ```
  }
  ```

> 
  ```
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.counts
  ```

> 
  ```
  foreach ($user in $users)
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($CsvFile -or $UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = Get-csOnlineUser -Identity $user
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  ```

> 
  ```
  Continue
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = $user
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  ```

> 
  ```
  Write-Host "The provider of $user has changed to Microsoft."
  ```

> 
  ```
  $enableUser
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  ```

> 
  ```
  continue;
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
   else
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Warning "The provider of $user is already set to Microsoft."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
              {
  ```

> 
  ```
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

Windows PowerShell の使い方の詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。
  
## 他に必要な情報はありますか?

- 1 人のユーザーに割り当てられるのは 1 つの電話会議プロバイダーのみです。
    
- いつでも電話会議プロバイダーをマイクロソフトからサードパーティのプロバイダーに変更することができます。詳細については、「[サードパーティを電話会議プロバイダーとして割り当てる](assign-a-third-party-as-the-audio-conferencing-provider.md)」をご覧ください。
    
- 組織内で、電話会議プロバイダーとして Microsoft を使用している人とサードパーティを使用している人が混在している場合があります。しかし、このような場合、設定と管理がより複雑になります。
    
## 関連トピック

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  

