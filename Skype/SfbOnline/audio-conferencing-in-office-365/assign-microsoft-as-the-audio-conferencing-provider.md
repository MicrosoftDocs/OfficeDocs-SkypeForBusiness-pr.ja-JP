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
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: dcf0eb1c4dcbfc5de54303e7d55538d3fcd6c007
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="ea3cc-103">Microsoft を電話会議プロバイダーとして割り当てる</span><span class="sxs-lookup"><span data-stu-id="ea3cc-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="ea3cc-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="ea3cc-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="ea3cc-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="ea3cc-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="ea3cc-108">Microsoft を電話会議プロバイダーとして割り当てる</span><span class="sxs-lookup"><span data-stu-id="ea3cc-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="ea3cc-109">Skype for Business 管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="ea3cc-109">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="ea3cc-110">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-110">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
2. <span data-ttu-id="ea3cc-111">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-111">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="ea3cc-112">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-112">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="ea3cc-113">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-113">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="ea3cc-114">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-114">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ea3cc-115">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-115">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="ea3cc-116">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-116">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="ea3cc-117">少数のユーザーのために Windows PowerShell スクリプトを使用する</span><span class="sxs-lookup"><span data-stu-id="ea3cc-117">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="ea3cc-118">時間を節約して自動化するために、次の PowerShell スクリプトを使用して、少数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-118">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="ea3cc-p104">プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-p104">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="ea3cc-121">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-121">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="ea3cc-122">多数のユーザーのために Windows PowerShell スクリプトを使用する</span><span class="sxs-lookup"><span data-stu-id="ea3cc-122">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="ea3cc-123">時間を節約して自動化するために、次の PowerShell スクリプトを使用して、多数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-123">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="ea3cc-p105">プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="ea3cc-126">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-126">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="ea3cc-127">**例 1:** 更新したいユーザーのリストを指定して、このスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-127">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="ea3cc-128">**例 2:** 更新したい各ユーザーの電子メール アドレス (エイリアス) を含む .csv ファイルを指定して、このスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-128">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="ea3cc-129">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-129">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="ea3cc-130">Here is the script:</span><span class="sxs-lookup"><span data-stu-id="ea3cc-130">Here is the script:</span></span>

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
<span data-ttu-id="ea3cc-131">Windows PowerShell の使い方の詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-131">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ea3cc-132">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ea3cc-132">Related topics</span></span>
<span data-ttu-id="ea3cc-133">[Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="ea3cc-133">[Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>

