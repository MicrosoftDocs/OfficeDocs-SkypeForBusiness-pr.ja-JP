---
title: Microsoft を電話会議プロバイダーとして割り当てる
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 74469a7686855d1bb17627282a9f2e5378a0d59e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237763"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Microsoft を電話会議プロバイダーとして割り当てる

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Microsoft 365 または Office 365 で Skype for Business および Microsoft Teams で電話会議を使用するには、組織内のユーザーに電話会議ライセンスが割り当てられている必要があります。 ライセンス[とコストの詳細については、「Microsoft 365](try-or-purchase-audio-conferencing-in-office-365.md)または Office 365 で電話会議を試用または購入する」を参照してください。

Microsoft の電話会議はダイヤルイン電話番号、PIN、会議 ID を提供します。会議の参加者はこれらを使用して組織の会議に参加することができます。 電話会議プロバイダーとして Microsoft を割り当てる必要があるのは、会議のスケジュールを設定または開催するユーザー Skype for BusinessまたはMicrosoft Teamsです。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Microsoft を電話会議プロバイダーとして割り当てる

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![ロゴを示Skype for Businessアイコン](../images/sfb-logo-30x30.png) Skype for Business 管理センターの使用

1. 管理センターの **[Microsoft Teams ポータル] に**  >  **移動します**。
    
2. [Skype for Business **センター] の左側** のナビゲーションで、[電話会議]**に移動します**。
    
3. バナーが表示されて「割り当てられた **電話会議** ライセンスはあるが、電話会議プロバイダーとしての Microsoft のセットがないユーザーが存在します」という通知を受けた場合は、[**クリックしてユーザーを移動**] をクリックします。 バナーが表示されない場合は、[**Skype for Business 管理センター**] で [**ユーザー**] をクリックし、[**電話会議に移動する準備のできたユーザー**] フィルターを選択します。
    
4. ユーザーのプロパティ ページの [プロバイダー名] で、ドロップダウン リストから **[Microsoft]** を選択します。
    
    > [!NOTE]
    > Microsoft を電話会議プロバイダーとして使用し、複数の電話番号を使用している場合は、[既定の有料電話番号] ドロップダウン リストを使用して、ユーザーの既定の音声番号を選択できます。
  
5. **[保存]** をクリックします。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>少数のユーザーのために Windows PowerShell スクリプトを使用する

時間を節約して自動化するために、次の PowerShell スクリプトを使用して、少数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。

> [!NOTE]
> プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。 

  
ユーザー数が少ないプロバイダーを Microsoft に変更するには  [、Enable-CsOnlineDialInConferencingUser コマンドレットを使用](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) できます。
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>多数のユーザーのために Windows PowerShell スクリプトを使用する
時間を節約して自動化するために、次の PowerShell スクリプトを使用して、多数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。

プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。 
  
PowerShell スクリプト ファイルに次のスクリプトを保存すると、どの入力パラメータを使用しても、そのスクリプトを実行できます。

**例 1:** 更新したいユーザーのリストを指定して、このスクリプトを実行できます。
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**例 2:** 更新したい各ユーザーの電子メール アドレス (エイリアス) を含む .csv ファイルを指定して、このスクリプトを実行できます。
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**例 3:** この例では、このスクリプトを使用して、組織内の多数のユーザーの電話会議プロバイダーを Intercall (または別のプロバイダー) から **Microsoft** に変更できます。
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  スクリプトを以下に示します。

  ```PowerShell
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
Windows PowerShell の使い方の詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)」をご覧ください。
  
## <a name="related-topics"></a>関連項目
[電話会議を試用または購入するには、Microsoft 365またはOffice 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
[Skype for Business Online を設定する](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
