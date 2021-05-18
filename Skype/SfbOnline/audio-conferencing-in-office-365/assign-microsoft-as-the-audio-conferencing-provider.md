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
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="c584d-103">Microsoft を電話会議プロバイダーとして割り当てる</span><span class="sxs-lookup"><span data-stu-id="c584d-103">Assign Microsoft as the audio conferencing provider</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="c584d-104">Microsoft 365 または Office 365 で Skype for Business および Microsoft Teams で電話会議を使用するには、組織内のユーザーに電話会議ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c584d-104">To use Audio Conferencing in Microsoft 365 or Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="c584d-105">ライセンス[とコストの詳細については、「Microsoft 365](try-or-purchase-audio-conferencing-in-office-365.md)または Office 365 で電話会議を試用または購入する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c584d-105">See [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="c584d-106">Microsoft の電話会議はダイヤルイン電話番号、PIN、会議 ID を提供します。会議の参加者はこれらを使用して組織の会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="c584d-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="c584d-107">電話会議プロバイダーとして Microsoft を割り当てる必要があるのは、会議のスケジュールを設定または開催するユーザー Skype for BusinessまたはMicrosoft Teamsです。</span><span class="sxs-lookup"><span data-stu-id="c584d-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="c584d-108">Microsoft を電話会議プロバイダーとして割り当てる</span><span class="sxs-lookup"><span data-stu-id="c584d-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![ロゴを示Skype for Businessアイコン](../images/sfb-logo-30x30.png) <span data-ttu-id="c584d-110">Skype for Business 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="c584d-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="c584d-111">管理センターの **[Microsoft Teams ポータル] に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="c584d-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="c584d-112">[Skype for Business **センター] の左側** のナビゲーションで、[電話会議]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="c584d-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c584d-113">バナーが表示されて「割り当てられた **電話会議** ライセンスはあるが、電話会議プロバイダーとしての Microsoft のセットがないユーザーが存在します」という通知を受けた場合は、[**クリックしてユーザーを移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c584d-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="c584d-114">バナーが表示されない場合は、[**Skype for Business 管理センター**] で [**ユーザー**] をクリックし、[**電話会議に移動する準備のできたユーザー**] フィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="c584d-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="c584d-115">ユーザーのプロパティ ページの [プロバイダー名] で、ドロップダウン リストから **[Microsoft]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c584d-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c584d-116">Microsoft を電話会議プロバイダーとして使用し、複数の電話番号を使用している場合は、[既定の有料電話番号] ドロップダウン リストを使用して、ユーザーの既定の音声番号を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c584d-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="c584d-117">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c584d-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="c584d-118">少数のユーザーのために Windows PowerShell スクリプトを使用する</span><span class="sxs-lookup"><span data-stu-id="c584d-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="c584d-119">時間を節約して自動化するために、次の PowerShell スクリプトを使用して、少数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。</span><span class="sxs-lookup"><span data-stu-id="c584d-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="c584d-p104">プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c584d-p104">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="c584d-122">ユーザー数が少ないプロバイダーを Microsoft に変更するには  [、Enable-CsOnlineDialInConferencingUser コマンドレットを使用](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) できます。</span><span class="sxs-lookup"><span data-stu-id="c584d-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="c584d-123">多数のユーザーのために Windows PowerShell スクリプトを使用する</span><span class="sxs-lookup"><span data-stu-id="c584d-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="c584d-124">時間を節約して自動化するために、次の PowerShell スクリプトを使用して、多数のユーザーのために Microsoft を電話会議プロバイダーとして設定することができます。</span><span class="sxs-lookup"><span data-stu-id="c584d-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="c584d-p105">プロバイダーが **Microsoft** に変更されるとき、ユーザーの電話会議情報 (電話会議 ID、有料電話番号と無料電話番号) が置き換えられます。プロバイダーを変更する前にこの情報を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c584d-p105">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced. You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="c584d-127">PowerShell スクリプト ファイルに次のスクリプトを保存すると、どの入力パラメータを使用しても、そのスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c584d-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="c584d-128">**例 1:** 更新したいユーザーのリストを指定して、このスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c584d-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="c584d-129">**例 2:** 更新したい各ユーザーの電子メール アドレス (エイリアス) を含む .csv ファイルを指定して、このスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c584d-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="c584d-130">**例 3:** この例では、このスクリプトを使用して、組織内の多数のユーザーの電話会議プロバイダーを Intercall (または別のプロバイダー) から **Microsoft** に変更できます。</span><span class="sxs-lookup"><span data-stu-id="c584d-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="c584d-131">スクリプトを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c584d-131">Here is the script:</span></span>

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
<span data-ttu-id="c584d-132">Windows PowerShell の使い方の詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c584d-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c584d-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="c584d-133">Related topics</span></span>
<span data-ttu-id="c584d-134">[電話会議を試用または購入するには、Microsoft 365またはOffice 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
[Skype for Business Online を設定する](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="c584d-134">[Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>
