---
title: Microsoft を電話会議プロバイダーとして割り当てる
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/02/2018
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
ms.openlocfilehash: d572c9fc61b887679e434e669fc263c746be8bcf
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Microsoft を電話会議プロバイダーとして割り当てる

Skype で Office 365 に電話会議を使用して、ビジネスおよびマイクロソフトのチーム、組織内のユーザーは各自に割り当てられた電話会議のライセンスを取得する必要があります。 ライセンスと、必要なコストの詳細については、 [Office 365 に電話会議を購入するか](try-or-purchase-audio-conferencing-in-office-365.md)を参照してください。

Microsoft オーディオ会議では、ダイヤルインの電話番号、Pin、および会議、組織の会議に参加するミーティングの参加者で使用できる Id を提供します。 オーディオ会議プロバイダーとしてマイクロソフトをスケジュールまたは Skype をビジネスまたはマイクロソフトのチーム会議をリードする人に割り当てる必要があるだけです。

**オーディオ会議の Microsoft**のライセンスが、オーディオ会議プロバイダーをインストールしていないユーザーに割り当てられている場合、ユーザーのプロバイダーを**マイクロソフト**に自動的に設定され、何も行う必要はありません。 場合は、ユーザーが既に、オーディオ会議プロバイダーを使用して、オーディオ会議のライセンスを割り当てることの後を Microsoft にユーザーのプロバイダーを変更する必要があります。

マイクロソフトは、オーディオ会議プロバイダーとして一覧表示されていることができる場合は、オーディオ会議のライセンスをユーザーに割り当てる必要があります。


  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Microsoft を電話会議プロバイダーとして割り当てる

### <a name="using-the-skype-for-business-admin-center"></a>Skype for Business 管理センターを使用する

1. Go to the **Office 365 admin center** > **Skype for Business**.
    
    > [!NOTE]
    > プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。 
  
2. **Skype**ビジネス管理センターは、左側のナビゲーションでは、[**電話会議**に移動します。
    
3. バナーが表示される場合が、**音声会議**をしているユーザーがあることを通知するライセンスは割り当てるが、マイクロソフトは、オーディオ会議プロバイダーとして設定いない場合、 **[**ここをクリックして移動する必要はありません。 バナーが表示されない場合、**ビジネス管理センターの Skype**で**ユーザー**] をクリックし、し、フィルターを選択、**ユーザーが電話会議に移動する準備ができて**。
    
4. [**プロバイダー名**] で、ユーザーの [プロパティ] ページのドロップダウン ボックスの一覧で**Microsoft**を選択します。
    
    > [!NOTE]
    > オーディオ会議プロバイダーとして、Microsoft を使用している複数の電話番号があるため、ユーザーの既定の音声番号を選択するのには、**有料電話番号が既定**のドロップ ダウン リストを使用できます。
  
5. [ **保存**] をクリックします。
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>少数のユーザーのために Windows PowerShell スクリプトを使用する

時間を節約して自動化するために、次の PowerShell スクリプトを使用して、少数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。

> [!NOTE]
> プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。 

  
マイクロソフトのユーザー数が少ないためにプロバイダーを変更するには、[有効にする CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx)コマンドレットを使用することができます。
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>多数のユーザーのために Windows PowerShell スクリプトを使用する
時間を節約して自動化するために、次の PowerShell スクリプトを使用して、多数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。

プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。 
  
PowerShell スクリプト ファイルに次のスクリプトを保存し、その入力パラメーターのいずれかを使用してそれを実行できます。

**例 1:** 更新したいユーザーのリストを指定して、このスクリプトを実行できます。
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

**例 2:** 更新したい各ユーザーの電子メール アドレス (エイリアス) を含む .csv ファイルを指定して、このスクリプトを実行できます。
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**例 3:**この例では、ことができますスクリプトを使用するこの Intercall からオーディオ会議プロバイダー (または別のプロバイダー) を変更するのには**マイクロソフト**に大規模な数のユーザーの組織内。
    
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
  
    
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

