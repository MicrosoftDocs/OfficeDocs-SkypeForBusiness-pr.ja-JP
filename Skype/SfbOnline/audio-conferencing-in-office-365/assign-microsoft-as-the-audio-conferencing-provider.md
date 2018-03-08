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
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="bd55d-104">電話会議プロバイダーとして Microsoft を割り当てる</span><span class="sxs-lookup"><span data-stu-id="bd55d-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="bd55d-p102">電話会議プロバイダーは*会議ブリッジ*を提供します。会議ブリッジにダイヤルイン電話番号、ピン、作成した会議の会議 Id を提供します。Skype を潜在顧客のビジネスまたは Microsoft チーム会議やスケジュールを設定する人に電話会議プロバイダーを割り当てる必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="bd55d-p102">An audio conferencing provider supplies the *conference bridge*. The conference bridge provides the dial-in phone numbers, PINs, and conference IDs for meetings that are created. You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
<span data-ttu-id="bd55d-108">オーディオのプロバイダーとして**Microsoft**が一覧表示されていることができる場合は、ユーザーに**電話会議**のライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd55d-108">If you want to be able to see **Microsoft** listed as the audio provider, you must assign an **Audio Conferencing** license to the user.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd55d-p103">サードパーティ電話会議プロバイダーに登録していない人に**電話会議**のライセンスを割り当てると、電話会議プロバイダーとして Microsoft が自動的に割り当てられます。必要な場合は、[サードパーティ電話会議プロバイダーとしての割り当て](assign-a-third-party-as-the-audio-conferencing-provider.md)をお試しください。</span><span class="sxs-lookup"><span data-stu-id="bd55d-p103">If you assign an **Audio Conferencing** license to a person who doesn't have a third-party audio conferencing provider, Microsoft is automatically assigned as the audio conferencing provider. You can [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) if needed.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="bd55d-111">電話会議プロバイダーとして Microsoft を割り当てる</span><span class="sxs-lookup"><span data-stu-id="bd55d-111">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="bd55d-112">Business 管理センターの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd55d-112">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="bd55d-113">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="bd55d-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bd55d-p104">プロバイダーは、別のプロバイダーから**Microsoft**に変更は、(会議 ID、有料フリー ダイヤルの番号) のユーザーの電話会議の情報が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd55d-p104">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="bd55d-116">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **ユーザー**の場合は、し、使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd55d-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>
    
3. <span data-ttu-id="bd55d-117">操作ウィンドウで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd55d-117">In the Action pane, click **Edit**.</span></span>
    
4. <span data-ttu-id="bd55d-118">[**プロバイダー名**] で、ユーザーの [プロパティ] ページには、ドロップダウン リストで**Microsoft**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd55d-118">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bd55d-119">電話会議プロバイダーとして Microsoft を使用して複数の電話番号があるため、**有料電話番号が既定**のドロップダウン リストを使用してユーザーの既定のオーディオ数を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="bd55d-119">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="bd55d-120">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="bd55d-120">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="bd55d-121">少数のユーザーの Windows PowerShell スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd55d-121">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="bd55d-122">時間を節約し、自動化したり、少数のユーザーの電話会議プロバイダーとして Microsoft を設定するのに次の PowerShell スクリプトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="bd55d-122">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="bd55d-p105">プロバイダーは、別のプロバイダーから**Microsoft**に変更は、(会議 ID、有料フリー ダイヤルの番号) のユーザーの電話会議の情報が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd55d-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="bd55d-125">次のスクリプトの 1 つ以上を PowerShell スクリプト ファイルとして保存し、それを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bd55d-125">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>
  
<span data-ttu-id="bd55d-126">少数のユーザーに Microsoft に、プロバイダーを変更するには、[有効にする CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd55d-126">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span></span>
  
<span data-ttu-id="bd55d-127">**例 1:**このスクリプトを実行するには、更新するユーザーのリストを提供します。</span><span class="sxs-lookup"><span data-stu-id="bd55d-127">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
<span data-ttu-id="bd55d-128">**例 2:**このスクリプトを実行するには、各ユーザーのメール アドレス (alias) を含む .csv ファイルを更新することを提供します。</span><span class="sxs-lookup"><span data-stu-id="bd55d-128">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="bd55d-129">多数のユーザーの Windows PowerShell スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd55d-129">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="bd55d-130">時間を節約し、自動化したり、次の PowerShell スクリプトを使用して多数のユーザーの電話会議プロバイダーとして Microsoft を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="bd55d-130">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="bd55d-p106">プロバイダーは、別のプロバイダーから**Microsoft**に変更は、(会議 ID、有料フリー ダイヤルの番号) のユーザーの電話会議の情報が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd55d-p106">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="bd55d-133">次のスクリプトの 1 つ以上を PowerShell スクリプト ファイルとして保存し、それを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bd55d-133">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>

<span data-ttu-id="bd55d-134">**例 1:**この例でこのスクリプト Intercall から電話会議プロバイダー (または別のプロバイダー) を変更するのに使える**Microsoft**大きい数値のユーザーの組織でします。</span><span class="sxs-lookup"><span data-stu-id="bd55d-134">**Example 1:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="bd55d-135">スクリプトを示します。</span><span class="sxs-lookup"><span data-stu-id="bd55d-135">Here is the script:</span></span>

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
<span data-ttu-id="bd55d-136">詳細については、Windows PowerShell を使用して、[共通の Skype for Business Online の管理タスクを実行する Windows PowerShell を使用する](https://go.microsoft.com/fwlink/?LinkId=525038)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd55d-136">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="bd55d-137">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="bd55d-137">What else should I know?</span></span>

- <span data-ttu-id="bd55d-138">ユーザーは、電話会議プロバイダーの 1 つだけ割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bd55d-138">A user can be assigned only one audio conferencing provider.</span></span>
    
- <span data-ttu-id="bd55d-p107">いつでも Microsoft からサードパーティ プロバイダーに電話会議プロバイダーを変更できます。詳細については、[電話会議プロバイダーとしてサードパーティの割り当て](assign-a-third-party-as-the-audio-conferencing-provider.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd55d-p107">You can change the audio conferencing provider from Microsoft to a third-party provider at any time. To learn more, see [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="bd55d-p108">自分の組織では、自分の電話会議プロバイダーとして Microsoft を使用している一部のユーザーと他のユーザーをサードパーティ プロバイダーを使用していることができます。セットアップし、管理をより複雑になります。</span><span class="sxs-lookup"><span data-stu-id="bd55d-p108">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider. But this is more complicated to set up and manage.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="bd55d-143">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bd55d-143">Related topics</span></span>

[<span data-ttu-id="bd55d-144">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="bd55d-144">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="bd55d-145">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="bd55d-145">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)