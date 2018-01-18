---
title: "Skype for Business と Microsoft Teams のライセンスを割り当てる"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: "電話システム、電話会議、計画を呼び出し、および通信のクレジットのビジネス ライセンスを Skype に割り当てる方法について説明します。 "
ms.openlocfilehash: d60d637d3b904b98ee8600647c57062927fe9afc
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="c4a03-103">Skype for Business と Microsoft Teams のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c4a03-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="c4a03-p101">この資料では、オーディオ会議、電話システム、および計画を呼び出すような機能をユーザーにライセンスを割り当てる方法のヒントを紹介します。一括でライセンスを割り当てるためのスクリプトも提供します。</span><span class="sxs-lookup"><span data-stu-id="c4a03-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>
  
 <span data-ttu-id="c4a03-106">**重要**: どのようなライセンス供与を受ける方法についてを参照してください[Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md)する必要があります購入と**購入方法**にによっては、Office 365 の計画では、オーディオ会議、フリー ダイヤル番号を表示するようにし、業務外の電話番号を呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="c4a03-106">**IMPORTANT**: See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="c4a03-107">電話システムと通話プラン: ライセンス割り当てのヒントとスクリプト</span><span class="sxs-lookup"><span data-stu-id="c4a03-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="c4a03-108">オーディオ会議、電話システム、および計画を呼び出してライセンスを割り当てる前に知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4a03-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="c4a03-p102">**ハイブリッド ユーザー向けにオンプレミス PSTN 接続を使用している場合** 、 **電話システム**のライセンスのみをユーザーに割り当てる必要があります。通話プランを割り当てる必要は **ありません** 。</span><span class="sxs-lookup"><span data-stu-id="c4a03-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>
    
- <span data-ttu-id="c4a03-112">**ライセンスの割り当て後の待機時間**: により、Office 365 とオンライン ビジネスの Skype との間の遅延時間、かかることが可能性のある割り当て計画を呼び出してライセンスを割り当てると、ユーザーには、最大で 24 時間です。</span><span class="sxs-lookup"><span data-stu-id="c4a03-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="c4a03-113">24 時間後に計画を呼び出すことがユーザーに割り当てされていない、[ビジネス製品の管理のヘルプのサポートに問い合わせてください](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。</span><span class="sxs-lookup"><span data-stu-id="c4a03-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>
    
- <span data-ttu-id="c4a03-p104">**エラー メッセージ**: 正確な数のライセンスを購入していないとエラー メッセージが表示されます。追加の通話プランのライセンスを購入する必要がある場合は、[ **追加購入**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c4a03-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="c4a03-116">**次のステップ**: ユーザー ライセンスの計画を呼び出すことを割り当てた後、組織の電話番号を取得し、組織内のユーザーにこれらの番号を割り当てる必要があります。。</span><span class="sxs-lookup"><span data-stu-id="c4a03-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="c4a03-117">手順の説明については、[計画を呼び出す設定](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4a03-117">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="c4a03-118">電話システムおよび通話プランのライセンスを 1 人のユーザーに対して割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="c4a03-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="c4a03-p106">手順は Office 365 ライセンスを割り当てる場合と同じです。「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4a03-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="c4a03-121">電話システムおよび通話プランのライセンスを一括で割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="c4a03-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="c4a03-122">**Microsoft オンライン サービス サインイン アシスタント RTW の IT プロフェッショナルのため**にインストールします。</span><span class="sxs-lookup"><span data-stu-id="c4a03-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="c4a03-123">モジュールがインストールされている必要はありませんか。</span><span class="sxs-lookup"><span data-stu-id="c4a03-123">Don't have the module installed?</span></span> <span data-ttu-id="c4a03-124">[Microsoft オンライン サービス サインイン アシスタントの IT プロフェッショナルの RTW](https://go.microsoft.com/fwlink/?LinkId=625123)をダウンロードして参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4a03-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>
    
2. <span data-ttu-id="c4a03-125">インストール、 **Windows Azure Active Directory のモジュール**。</span><span class="sxs-lookup"><span data-stu-id="c4a03-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="c4a03-126">モジュールがインストールされている必要はありませんか。</span><span class="sxs-lookup"><span data-stu-id="c4a03-126">Don't have the module installed?</span></span> <span data-ttu-id="c4a03-127">ダウンロードの手順とコマンドレットの構文については、 [Windows PowerShell を使用して AD を Azure の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4a03-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
3. <span data-ttu-id="c4a03-128">モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c4a03-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
  <span data-ttu-id="c4a03-129">この例では、 **Enterprise E3 ライセンス** と、 **電話システム** および **国内通話プラン** ライセンスを割り当てています。</span><span class="sxs-lookup"><span data-stu-id="c4a03-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>
    
  <span data-ttu-id="c4a03-130">スクリプト内のライセンスの名前または製品名は、斜体で表示されています (下記の例と、その次の「 **スクリプトで使用される電話システムと通話プランの製品名または SKU** 」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="c4a03-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>
    
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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="c4a03-131">スクリプトで使用される電話システムと通話プランの製品名または SKU</span><span class="sxs-lookup"><span data-stu-id="c4a03-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="c4a03-132">**製品名**</span><span class="sxs-lookup"><span data-stu-id="c4a03-132">**Product name**</span></span>|<span data-ttu-id="c4a03-133">**SKU 部品名**</span><span class="sxs-lookup"><span data-stu-id="c4a03-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c4a03-134">エンタープライズ E5 (電話システムあり)</span><span class="sxs-lookup"><span data-stu-id="c4a03-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="c4a03-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="c4a03-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="c4a03-136">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="c4a03-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="c4a03-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="c4a03-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="c4a03-138">エンタープライズ E1</span><span class="sxs-lookup"><span data-stu-id="c4a03-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="c4a03-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="c4a03-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="c4a03-140">Skype for Business オンライン スタンドアロンプラン 2</span><span class="sxs-lookup"><span data-stu-id="c4a03-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="c4a03-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="c4a03-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="c4a03-142">電話システム</span><span class="sxs-lookup"><span data-stu-id="c4a03-142">Phone System</span></span>  <br/> |<span data-ttu-id="c4a03-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="c4a03-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="c4a03-144">国際通話プラン</span><span class="sxs-lookup"><span data-stu-id="c4a03-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="c4a03-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="c4a03-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="c4a03-146">国内通話プラン</span><span class="sxs-lookup"><span data-stu-id="c4a03-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="c4a03-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="c4a03-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="c4a03-148">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="c4a03-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="c4a03-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="c4a03-149">MCOPSTNPP</span></span>  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="c4a03-150">電話会議: ライセンス割り当てのヒントとスクリプト</span><span class="sxs-lookup"><span data-stu-id="c4a03-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="c4a03-151">電話会議のライセンス割り当て前に知っておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c4a03-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="c4a03-p109">**サードパーティの電話会議プロバイダー**: サードパーティの電話会議プロバイダーを使用するように他のユーザーによって既に設定されている場合に、 **電話会議**ライセンスを割り当てると、電話会議プロバイダーとして Microsoft を使用するように変更されます。この設定を変更して、サードパーティ プロバイダーに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="c4a03-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>
    
- <span data-ttu-id="c4a03-154">次の手順:**オーディオ会議**のライセンスを割り当てると、する必要があります、オーディオ会議プロバイダーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c4a03-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="c4a03-155">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c4a03-155">Do one of the following:</span></span>
    
  - [<span data-ttu-id="c4a03-156">Microsoft を電話会議プロバイダーとして割り当てる</span><span class="sxs-lookup"><span data-stu-id="c4a03-156">Assign Microsoft as the audio conferencing provider</span></span>](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - <span data-ttu-id="c4a03-157">または、[サードパーティを電話会議プロバイダーとして割り当てる](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span><span class="sxs-lookup"><span data-stu-id="c4a03-157">Or, [Assign a third-party as the audio conferencing provider](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span></span>
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="c4a03-158">電話会議ライセンスを 1 人のユーザーに対して割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="c4a03-158">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="c4a03-p111">手順は Office 365 ライセンスを割り当てる場合と同じです。「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4a03-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="c4a03-161">電話会議ライセンスを一括で割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="c4a03-161">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="c4a03-162">[IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="c4a03-162">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>
    
2. <span data-ttu-id="c4a03-p112">**Windows Azure Active Directory モジュール** をダウンロードしてインストールします。ダウンロードの手順とコマンドレットの構文については、「[Windows PowerShell による Azure AD の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4a03-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
    <span data-ttu-id="c4a03-165">モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c4a03-165">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
    <span data-ttu-id="c4a03-166">斜体のテキストでは、ライセンスの名前、またはスクリプト内で製品名が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4a03-166">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="c4a03-167">[オーディオ会議の製品名やスクリプト作成に使用する製品](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)のすべての製品名を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4a03-167">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>
    
    <span data-ttu-id="c4a03-168">この例では、Enterprise E3 ライセンスと電話会議ライセンスを割り当てています。</span><span class="sxs-lookup"><span data-stu-id="c4a03-168">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>
    
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="c4a03-169">スクリプトで使用される音声会議の製品名または SKU</span><span class="sxs-lookup"><span data-stu-id="c4a03-169">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="c4a03-170"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="c4a03-170"></span></span>

|<span data-ttu-id="c4a03-171">**製品名**</span><span class="sxs-lookup"><span data-stu-id="c4a03-171">**Product name**</span></span>|<span data-ttu-id="c4a03-172">**SKU 部品名**</span><span class="sxs-lookup"><span data-stu-id="c4a03-172">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c4a03-173">電話会議</span><span class="sxs-lookup"><span data-stu-id="c4a03-173">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="c4a03-174">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="c4a03-174">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="c4a03-175">Skype for Business オンライン スタンドアロンプラン 2</span><span class="sxs-lookup"><span data-stu-id="c4a03-175">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="c4a03-176">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="c4a03-176">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="c4a03-177">エンタープライズ E1</span><span class="sxs-lookup"><span data-stu-id="c4a03-177">Enterprise E1</span></span>  <br/> |<span data-ttu-id="c4a03-178">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="c4a03-178">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="c4a03-179">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="c4a03-179">Enterprise E3</span></span>  <br/> |<span data-ttu-id="c4a03-180">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="c4a03-180">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="c4a03-181">Enterprise E5 (電話会議なし)</span><span class="sxs-lookup"><span data-stu-id="c4a03-181">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="c4a03-182">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="c4a03-182">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="c4a03-183">Enterprise E5 (電話会議あり)</span><span class="sxs-lookup"><span data-stu-id="c4a03-183">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="c4a03-184">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="c4a03-184">ENTERPRISEPREMIUM</span></span>  <br/> |
   
## <a name="communications-credits"></a><span data-ttu-id="c4a03-185">通信クレジット</span><span class="sxs-lookup"><span data-stu-id="c4a03-185">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="c4a03-186">通信クレジットのライセンス割り当て前に知っておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c4a03-186">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="c4a03-187">**E5 のエンタープライズのお客様**: ユーザーがエンタープライズ E5 のライセンスを割り当てられている場合でもをお勧めするユーザーを割り当てる**通信のクレジット**のライセンスです。</span><span class="sxs-lookup"><span data-stu-id="c4a03-187">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="c4a03-188">**次の手順**: これらのライセンスを割り当てると後の組織では、自分の電話番号を取得し、組織内のユーザーにこれらの番号を割り当てる必要があります。。</span><span class="sxs-lookup"><span data-stu-id="c4a03-188">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="c4a03-189">手順の説明については、[計画を呼び出す設定](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4a03-189">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="c4a03-190">通信クレジットのライセンスを 1 人のユーザーに対して割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="c4a03-190">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="c4a03-p115">手順は Office 365 ライセンスを割り当てる場合と同じです。「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4a03-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="c4a03-193">大量の通信のクレジットのライセンスを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="c4a03-193">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="c4a03-p116">**電話会議**ライセンスを割り当てるサンプル スクリプトを確認します。その情報を、 **通信クレジット**のライセンスを割り当てるための情報で更新します。</span><span class="sxs-lookup"><span data-stu-id="c4a03-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c4a03-196">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c4a03-196">Related topics</span></span>

[<span data-ttu-id="c4a03-197">Skype for Business および Microsoft Teams の電話会議のセットアップ</span><span class="sxs-lookup"><span data-stu-id="c4a03-197">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[<span data-ttu-id="c4a03-198">通話プランのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c4a03-198">Set up Calling Plans</span></span>](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[<span data-ttu-id="c4a03-199">資金を追加し、通信のクレジットの管理</span><span class="sxs-lookup"><span data-stu-id="c4a03-199">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
  