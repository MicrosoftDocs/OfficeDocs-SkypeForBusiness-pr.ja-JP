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
ms.openlocfilehash: f0c3d1d667847e080b47f31bb1032ff4b8ac980d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695762"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Microsoft を電話会議プロバイダーとして割り当てる

Skype for Business と Microsoft Teams で Office 365 の電話会議を使用するには、組織内のユーザーは、それらに割り当てる電話会議ライセンスを取得する必要があります。 ライセンス付与と必要コストの詳細については、 [Office 365 の電話会議のトライアルと購入](try-or-purchase-audio-conferencing-in-office-365.md) を参照してください。

Microsoft の電話会議はダイヤルイン電話番号、PIN、会議 ID を提供します。会議の参加者はこれらを使用して組織の会議に参加することができます。 Skype for Business または Microsoft Teams の会議をスケジュールまたは開催しようとしているユーザーには、Microsoft を電話会議プロバイダーとして割り当てる必要があります。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Microsoft を電話会議プロバイダーとして割り当てる

### <a name="an-icon-showing-the-skype-for-business-logoimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![Skype for Business ロゴを示すアイコン](../images/sfb-logo-30x30.png) Skype for Business 管理センターの使用

1. **Microsoft Teams 管理センター** > の**従来のポータル**に移動します。
    
2. **Skype For business 管理センター**の左側のナビゲーションで、[**電話会議**] に移動します。
    
3. バナーが表示されて「割り当てられた**電話会議** ライセンスはあるが、電話会議プロバイダーとしての Microsoft のセットがないユーザーが存在します」という通知を受けた場合は、[**クリックしてユーザーを移動**] をクリックします。 バナーが表示されない場合は、[**Skype for Business 管理センター**] で [**ユーザー**] をクリックし、[**電話会議に移動する準備のできたユーザー**] フィルターを選択します。
    
4. ユーザーのプロパティページの [**プロバイダー名**] で、ドロップダウンリストから [ **Microsoft** ] を選びます。
    
    > [!NOTE]
    > Microsoft を電話会議プロバイダーとして使用していて、複数の電話番号があるため、[**既定の有料**電話番号] ドロップダウンリストを使用して、ユーザーの既定のオーディオ番号を選ぶことができます。
  
5. **[保存]** をクリックします。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>少数のユーザーのために Windows PowerShell スクリプトを使用する

時間を節約して自動化するために、次の PowerShell スクリプトを使用して、少数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。

> [!NOTE]
> プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。 

  
少数のユーザーのためにプロバイダーを Microsoft に変更するには、 [get-csonlinedialinconferencinguser](https://technet.microsoft.com/library/mt243813.aspx)コマンドレットを使用します。
  

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

**使用例 3:** この例では、組織内の多数のユーザーに対して、このスクリプトを使用して、電話会議プロバイダーを Intercall (または別のプロバイダー) から**Microsoft**に変更できます。
    
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
Windows PowerShell の使い方の詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック
[Office 365 の電話会議のトライアルと購入](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Skype for Business Online の設定](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

