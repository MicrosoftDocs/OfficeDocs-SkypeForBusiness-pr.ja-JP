---
title: "ライセンスのビジネスと Microsoft チームの Skype を割り当てる"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
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
- Licensing
- Strat_SB_PSTN
description: "Skype を電話システムで、音声会議、プランの呼び出し] との通信を加算したものビジネス ライセンスを割り当てる方法について説明します。 "
ms.openlocfilehash: a5cbc36d1b5ce5a7d79587df369b2d3bf3caacd6
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="b92e5-103">ライセンスのビジネスと Microsoft チームの Skype を割り当てる</span><span class="sxs-lookup"><span data-stu-id="b92e5-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="b92e5-p101">この記事では、音声会議、電話システムでは、プランの呼び出しなどの機能をユーザーにライセンスを割り当てに関するヒントを紹介します。一括のライセンスを割り当てるスクリプトも提供します。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>
  
 <span data-ttu-id="b92e5-106">**重要**:」をご覧ください[Skype for Business や Microsoft チーム アドオンのライセンス](skype-for-business-and-microsoft-teams-add-on-licensing.md)についてはどのようなライセンスをする必要があります購入し、**購入する方法**にによっては、Office 365 プランのため、ユーザーは、音声会議、フリー ダイヤルの番号を取得し、組織外の電話番号を呼び出す機能。</span><span class="sxs-lookup"><span data-stu-id="b92e5-106">**IMPORTANT**: See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="b92e5-107">電話システムとプランの呼び出し: のヒントとライセンスの割り当てについてスクリプト</span><span class="sxs-lookup"><span data-stu-id="b92e5-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="b92e5-108">音声会議、電話システムやライセンスの割り当ての呼び出しを計画する前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="b92e5-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="b92e5-p102">**ハイブリッド ユーザーの内部設置型 PSTN への接続を使用してよいですか?**必要な場合は、のみ、**電話システムで**ライセンスを割り当てる必要があります。呼び出し計画割り当て**いない**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>
    
- <span data-ttu-id="b92e5-p103">**ライセンスの割り当て後の待機時間**: の理由により、Office 365 と Skype for Business Online の間、待機時間かかることがおそらくまで 24 時間が割り当てられている呼び出し計画ライセンスの割り当て後にします。24 時間後に通話プランがユーザーに割り当てされていない、 [business 製品 - 管理者向けヘルプのサポートに問い合わせてください](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>
    
- <span data-ttu-id="b92e5-p104">**エラー メッセージ**: 適切なライセンス数を購入していない場合、エラー メッセージが表示されます。その他のプランの呼び出しのライセンスを購入する必要がある場合は、**さらに購入**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="b92e5-p105">**次のステップ**: 通話プランのライセンスの割り当てをユーザーに後、を組織の電話番号を取得し、[これらの数値を組織のユーザーに割り当てる必要があります。詳しい手順については、[プランの呼び出しを設定する](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="b92e5-118">1 人のユーザーに電話システムとプランの呼び出しのライセンスを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="b92e5-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="b92e5-p106">手順は、Office 365 のライセンスを割り当てると同じです。[割り当てまたは一般法人向け Office 365 のライセンスを削除する](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="b92e5-121">一括電話システムとプランの呼び出しのライセンスを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="b92e5-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="b92e5-p107">**Microsoft Online Services サインイン アシスタント IT プロフェッショナル向け RTW**をインストールします。インストールされているモジュールを作成されていない場合[Microsoft Online Services サインイン アシスタント IT プロフェッショナル RTW の](https://go.microsoft.com/fwlink/?LinkId=625123)ダウンロードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>
    
2. <span data-ttu-id="b92e5-p108">インストール、 **Windows Azure Active Directory モジュール**。インストールされているモジュールを作成されていない場合ダウンロードの手順とコマンドレットの書式には、[管理 Windows PowerShell を使用して Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
3. <span data-ttu-id="b92e5-128">インストールされているモジュールを取得するには、ユーザーのライセンスを割り当てる Windows PowerShell コマンド プロンプトと、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b92e5-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
  <span data-ttu-id="b92e5-129">この例では、**電話システム**と、**国内通話プラン**のライセンスと**Enterprise E3 ライセンス**を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b92e5-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>
    
  <span data-ttu-id="b92e5-130">ライセンスの名前や、スクリプトで製品名斜体のテキストに表示されます (例の後、**電話システムでは、製品名のプランの呼び出しまたは Sku のスクリプトの実行に使用**することを参照)。</span><span class="sxs-lookup"><span data-stu-id="b92e5-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
  
  #Example of text file:
  #user1@domain.com
  #user2@domain.com
  
  #Import Module
  ipmo MSOnline
  #Authenticate to MSOLservice.
  Connect-MSOLService
  #File prompt to select the userlist txt file.
  [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename
  If ($OFD.filename -eq '')
  {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
  }
  #Create a variable of all users.
  $users = Get-Content $OFD.filename
  #License each user in the $users variable.
  #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
  International Calling.
  for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 
  ```
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="b92e5-131">電話システムとプランの呼び出しの製品名や Sku のスクリプトの実行を使用します。</span><span class="sxs-lookup"><span data-stu-id="b92e5-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="b92e5-132">**製品名**</span><span class="sxs-lookup"><span data-stu-id="b92e5-132">**Product name**</span></span>|<span data-ttu-id="b92e5-133">**SKU 部品名**</span><span class="sxs-lookup"><span data-stu-id="b92e5-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b92e5-134">[エンタープライズの E5 (された電話システムで対応)</span><span class="sxs-lookup"><span data-stu-id="b92e5-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="b92e5-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b92e5-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="b92e5-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="b92e5-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="b92e5-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b92e5-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="b92e5-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="b92e5-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="b92e5-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b92e5-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="b92e5-140">Skype for Business Online スタンドアロン プラン 2</span><span class="sxs-lookup"><span data-stu-id="b92e5-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="b92e5-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="b92e5-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="b92e5-142">電話システム</span><span class="sxs-lookup"><span data-stu-id="b92e5-142">Phone System</span></span>  <br/> |<span data-ttu-id="b92e5-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="b92e5-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="b92e5-144">国際通話プラン</span><span class="sxs-lookup"><span data-stu-id="b92e5-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="b92e5-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="b92e5-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="b92e5-146">国内通話プラン</span><span class="sxs-lookup"><span data-stu-id="b92e5-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="b92e5-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="b92e5-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="b92e5-148">通信を加算したもの</span><span class="sxs-lookup"><span data-stu-id="b92e5-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="b92e5-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="b92e5-149">MCOPSTNPP</span></span>  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="b92e5-150">電話会議の場合: のヒントとライセンスの割り当てについてスクリプト</span><span class="sxs-lookup"><span data-stu-id="b92e5-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="b92e5-151">電話会議ライセンスを割り当てる前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="b92e5-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="b92e5-p109">**サードパーティ電話会議プロバイダー**:**電話会議**のライセンスを割り当てると、サードパーティ電話会議プロバイダーを使用するようにセットアップする他のユーザーが既にと、この電話会議として Microsoft を使用することを変更します。プロバイダーです。サードパーティ プロバイダーに戻るには、これらを変更できます。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>
    
- <span data-ttu-id="b92e5-p110">次の手順:**電話会議**ライセンスを割り当てたら、電話会議プロバイダーを割り当てるする必要があります。{次のいずれかを行います。}</span><span class="sxs-lookup"><span data-stu-id="b92e5-p110">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider. Do one of the following:</span></span>
    
  - [<span data-ttu-id="b92e5-156">電話会議プロバイダーとして Microsoft を割り当てる</span><span class="sxs-lookup"><span data-stu-id="b92e5-156">Assign Microsoft as the audio conferencing provider</span></span>](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - <span data-ttu-id="b92e5-157">または、[電話会議プロバイダーとしてサードパーティの割り当て](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span><span class="sxs-lookup"><span data-stu-id="b92e5-157">Or, [Assign a third-party as the audio conferencing provider](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span></span>
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="b92e5-158">1 人のユーザーに電話会議のライセンスを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="b92e5-158">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="b92e5-p111">手順は、Office 365 のライセンスを割り当てると同じです。[割り当てまたは一般法人向け Office 365 のライセンスを削除する](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="b92e5-161">一括で電話会議ライセンスを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="b92e5-161">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="b92e5-162">ダウンロードして、 [Microsoft Online Services サインイン アシスタント IT プロフェッショナル RTW を](https://go.microsoft.com/fwlink/?LinkId=625123)インストールします。</span><span class="sxs-lookup"><span data-stu-id="b92e5-162">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>
    
2. <span data-ttu-id="b92e5-p112">ダウンロード、インストール、 **Windows Azure Active Directory モジュール**。ダウンロードの手順とコマンドレットの書式には、[管理 Windows PowerShell を使用して Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
    <span data-ttu-id="b92e5-165">インストールされているモジュールを取得するには、ユーザーのライセンスを割り当てる Windows PowerShell コマンド プロンプトと、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b92e5-165">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
    <span data-ttu-id="b92e5-p113">斜体のテキストのスクリプトの商品名またはライセンスの名前が表示されます。[電話会議の製品名または Sku のスクリプトの実行するため](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)のすべての製品名を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p113">The name of the licenses or product names in the script are listed in italics text. See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>
    
    <span data-ttu-id="b92e5-168">この例では、音声会議ライセンスをと共に Enterprise E3 ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b92e5-168">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>
    
```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline

#Authenticate to MSOLservice
Connect-MSOLService
#File prompt to select the userlist txt file
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename

If ($OFD.filename -eq '')
{
Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}

#Create a variable of all users
$users = Get-Content $OFD.filename

#License each user in the $users variable
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    } 
```

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="b92e5-169">音声会議製品名または Sku のスクリプトの実行を使用します。</span><span class="sxs-lookup"><span data-stu-id="b92e5-169">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="b92e5-170"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="b92e5-170"></span></span>

|<span data-ttu-id="b92e5-171">**製品名**</span><span class="sxs-lookup"><span data-stu-id="b92e5-171">**Product name**</span></span>|<span data-ttu-id="b92e5-172">**SKU 部品名**</span><span class="sxs-lookup"><span data-stu-id="b92e5-172">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b92e5-173">電話会議</span><span class="sxs-lookup"><span data-stu-id="b92e5-173">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="b92e5-174">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="b92e5-174">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="b92e5-175">Skype for Business Online スタンドアロン プラン 2</span><span class="sxs-lookup"><span data-stu-id="b92e5-175">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="b92e5-176">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="b92e5-176">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="b92e5-177">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="b92e5-177">Enterprise E1</span></span>  <br/> |<span data-ttu-id="b92e5-178">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b92e5-178">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="b92e5-179">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="b92e5-179">Enterprise E3</span></span>  <br/> |<span data-ttu-id="b92e5-180">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b92e5-180">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="b92e5-181">エンタープライズの E5 (せずに電話会議の場合)</span><span class="sxs-lookup"><span data-stu-id="b92e5-181">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="b92e5-182">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="b92e5-182">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="b92e5-183">(電話会議) がエンタープライズ E5</span><span class="sxs-lookup"><span data-stu-id="b92e5-183">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="b92e5-184">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b92e5-184">ENTERPRISEPREMIUM</span></span>  <br/> |
   
## <a name="communications-credits"></a><span data-ttu-id="b92e5-185">通信を加算したもの</span><span class="sxs-lookup"><span data-stu-id="b92e5-185">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="b92e5-186">通信クレジットのライセンスを割り当てる前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="b92e5-186">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="b92e5-187">**エンタープライズ E5 顧客**: 場合でも、ユーザーには、エンタープライズ E5 ライセンスが割り当てられているが、まだをお勧めするライセンスを割り当てることに**コミュニケーションを加算したもの**です。</span><span class="sxs-lookup"><span data-stu-id="b92e5-187">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="b92e5-p114">**次のステップ**: これらのライセンスの割り当て後を組織の電話番号を取得し、[これらの数値を組織のユーザーに割り当てる必要があります。詳しい手順については、[プランの呼び出しを設定する](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p114">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="b92e5-190">1 人のユーザーに通信クレジットのライセンスを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="b92e5-190">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="b92e5-p115">手順は、Office 365 のライセンスを割り当てると同じです。[割り当てまたは一般法人向け Office 365 のライセンスを削除する](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="b92e5-193">一括で通信クレジットのライセンスを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="b92e5-193">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="b92e5-p116">**電話会議**ライセンスを割り当てるためのサンプル スクリプトを参照してください。**通信クレジット**のライセンスの割り当てについての情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="b92e5-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b92e5-196">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b92e5-196">Related topics</span></span>

[<span data-ttu-id="b92e5-197">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="b92e5-197">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[<span data-ttu-id="b92e5-198">プランの呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="b92e5-198">Set up Calling Plans</span></span>](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[<span data-ttu-id="b92e5-199">金を追加およびクレジットの通信を管理します。</span><span class="sxs-lookup"><span data-stu-id="b92e5-199">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
  