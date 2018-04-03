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
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="0a2b1-104">Microsoft を電話会議プロバイダーとして割り当てる</span><span class="sxs-lookup"><span data-stu-id="0a2b1-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="0a2b1-105">Skype で Office 365 に電話会議を使用して、ビジネスおよびマイクロソフトのチーム、組織内のユーザーは各自に割り当てられた電話会議のライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-105">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="0a2b1-106">ライセンスと、必要なコストの詳細については、 [Office 365 に電話会議を購入するか](try-or-purchase-audio-conferencing-in-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-106">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="0a2b1-107">Microsoft オーディオ会議では、ダイヤルインの電話番号、Pin、および会議、組織の会議に参加するミーティングの参加者で使用できる Id を提供します。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-107">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="0a2b1-108">オーディオ会議プロバイダーとしてマイクロソフトをスケジュールまたは Skype をビジネスまたはマイクロソフトのチーム会議をリードする人に割り当てる必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-108">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

<span data-ttu-id="0a2b1-109">**オーディオ会議の Microsoft**のライセンスが、オーディオ会議プロバイダーをインストールしていないユーザーに割り当てられている場合、ユーザーのプロバイダーを**マイクロソフト**に自動的に設定され、何も行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-109">If a **Microsoft Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to **Microsoft** and you don't have to do anything else.</span></span> <span data-ttu-id="0a2b1-110">場合は、ユーザーが既に、オーディオ会議プロバイダーを使用して、オーディオ会議のライセンスを割り当てることの後を Microsoft にユーザーのプロバイダーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-110">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an Audio Conferencing license.</span></span>

<span data-ttu-id="0a2b1-111">マイクロソフトは、オーディオ会議プロバイダーとして一覧表示されていることができる場合は、オーディオ会議のライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-111">If you want to be able to see Microsoft listed as the audio conferencing provider, you must assign an Audio Conferencing license to the user.</span></span>


  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="0a2b1-112">Microsoft を電話会議プロバイダーとして割り当てる</span><span class="sxs-lookup"><span data-stu-id="0a2b1-112">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="0a2b1-113">Skype for Business 管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="0a2b1-113">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="0a2b1-114">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="0a2b1-114">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0a2b1-p105">プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="0a2b1-117">**Skype**ビジネス管理センターは、左側のナビゲーションでは、[**電話会議**に移動します。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-117">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="0a2b1-118">バナーが表示される場合が、**音声会議**をしているユーザーがあることを通知するライセンスは割り当てるが、マイクロソフトは、オーディオ会議プロバイダーとして設定いない場合、 **[**ここをクリックして移動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-118">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="0a2b1-119">バナーが表示されない場合、**ビジネス管理センターの Skype**で**ユーザー**] をクリックし、し、フィルターを選択、**ユーザーが電話会議に移動する準備ができて**。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-119">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="0a2b1-120">[**プロバイダー名**] で、ユーザーの [プロパティ] ページのドロップダウン ボックスの一覧で**Microsoft**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-120">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0a2b1-121">オーディオ会議プロバイダーとして、Microsoft を使用している複数の電話番号があるため、ユーザーの既定の音声番号を選択するのには、**有料電話番号が既定**のドロップ ダウン リストを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-121">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="0a2b1-122">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-122">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="0a2b1-123">少数のユーザーのために Windows PowerShell スクリプトを使用する</span><span class="sxs-lookup"><span data-stu-id="0a2b1-123">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="0a2b1-124">時間を節約して自動化するために、次の PowerShell スクリプトを使用して、少数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="0a2b1-p107">プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-p107">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="0a2b1-127">マイクロソフトのユーザー数が少ないためにプロバイダーを変更するには、[有効にする CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-127">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="0a2b1-128">多数のユーザーのために Windows PowerShell スクリプトを使用する</span><span class="sxs-lookup"><span data-stu-id="0a2b1-128">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="0a2b1-129">時間を節約して自動化するために、次の PowerShell スクリプトを使用して、多数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-129">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="0a2b1-p108">プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-p108">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="0a2b1-132">PowerShell スクリプト ファイルに次のスクリプトを保存し、その入力パラメーターのいずれかを使用してそれを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-132">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="0a2b1-133">**例 1:** 更新したいユーザーのリストを指定して、このスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-133">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="0a2b1-134">**例 2:** 更新したい各ユーザーの電子メール アドレス (エイリアス) を含む .csv ファイルを指定して、このスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-134">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="0a2b1-135">**例 3:**この例では、ことができますスクリプトを使用するこの Intercall からオーディオ会議プロバイダー (または別のプロバイダー) を変更するのには**マイクロソフト**に大規模な数のユーザーの組織内。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-135">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="0a2b1-136">スクリプトを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-136">Here is the script:</span></span>

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
<span data-ttu-id="0a2b1-137">Windows PowerShell の使い方の詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-137">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="0a2b1-138">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0a2b1-138">Related topics</span></span>

[<span data-ttu-id="0a2b1-139">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="0a2b1-139">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
[<span data-ttu-id="0a2b1-140">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="0a2b1-140">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

