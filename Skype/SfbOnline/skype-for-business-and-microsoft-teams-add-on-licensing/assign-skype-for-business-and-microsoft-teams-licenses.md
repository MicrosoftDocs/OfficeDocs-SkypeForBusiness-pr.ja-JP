---
title: Skype for Business と Microsoft Teams のライセンスを割り当てる
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Licensing
description: '電話システム、電話会議、通話プランやコミュニケーション クレジットを使用するために Skype for Business  のライセンスを割り当てる方法について説明します。 '
ms.openlocfilehash: af2b7357c5dbe9e11b84ac87e0f72721d10a6a30
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856055"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="44a6b-103">Skype for Business と Microsoft Teams のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="44a6b-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="44a6b-104">この記事では、ユーザーに電話会議、電話システムや通話プランなどの機能のためにライセンスを割り当てる際のヒントを紹介します。</span><span class="sxs-lookup"><span data-stu-id="44a6b-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System and Calling Plans.</span></span> <span data-ttu-id="44a6b-105">また、ライセンスを一括で割り当てるスクリプトも提供します。</span><span class="sxs-lookup"><span data-stu-id="44a6b-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44a6b-106">電話会議やフリーダイアル電話番号を利用したり、社外から電話をかけるために購入が必要な Office 365 プランごとのライセンスの詳細について、およびそれらの[  購入方法](skype-for-business-and-microsoft-teams-add-on-licensing.md) については、「\*\*  Skype for Business と Microsoft Teams のアドオン ライセンス\*\* 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44a6b-106">IMPORTANT: See[Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="44a6b-107">電話システムと通話プラン: ライセンス割り当てのヒントとスクリプト</span><span class="sxs-lookup"><span data-stu-id="44a6b-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="44a6b-108">電話会議、電話システムおよび通話プランのライセンス割り当て前に知っておくべき情報</span><span class="sxs-lookup"><span data-stu-id="44a6b-108">What you need to know before assigning Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="44a6b-p102">**ハイブリッド ユーザー向けにオンプレミス PSTN 接続を使用している場合** 、 **電話システム**のライセンスのみをユーザーに割り当てる必要があります。通話プランを割り当てる必要は **ありません** 。</span><span class="sxs-lookup"><span data-stu-id="44a6b-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="44a6b-112">**ライセンス割り当て後の遅延**: Office 365 と Skype for Business Online の間に遅延時間があるため、ユーザーにライセンスを割り当てた後、そのユーザーに通話プランが割り当てられるまでに、最大で 24 時間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="44a6b-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="44a6b-113">24 時間経過してもユーザーに通話プランが割り当てられない場合は、「[一般法人向けサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44a6b-113">If after 24 hours, the user isn't assigned a Calling Plan please[Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="44a6b-p104">**エラー メッセージ**: 正確な数のライセンスを購入していないとエラー メッセージが表示されます。追加の通話プランのライセンスを購入する必要がある場合は、[ **追加購入**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="44a6b-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="44a6b-116">**次の手順**: ユーザーに通話プランのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="44a6b-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="44a6b-117">詳しい手順については、「[通話プランのセットアップ](/microsoftteams/set-up-calling-plans)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44a6b-117">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="44a6b-118">電話システムおよび通話プランのライセンスを 1 人のユーザーに対して割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="44a6b-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="44a6b-p106">手順は Office 365 ライセンスを割り当てる場合と同じです。「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44a6b-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="44a6b-121">電話システムおよび通話プランのライセンスを一括で割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="44a6b-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="44a6b-122">**IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW** をインストールします。</span><span class="sxs-lookup"><span data-stu-id="44a6b-122">Download and install **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="44a6b-123">このモジュールがインストールされていない場合は、</span><span class="sxs-lookup"><span data-stu-id="44a6b-123">Don't have the module installed?</span></span> <span data-ttu-id="44a6b-124">[IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) を参照してダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="44a6b-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="44a6b-125">**Windows Azure Active Directory モジュール** をインストールします。</span><span class="sxs-lookup"><span data-stu-id="44a6b-125">Download and install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="44a6b-126">このモジュールがインストールされていない場合は、</span><span class="sxs-lookup"><span data-stu-id="44a6b-126">Don't have the module installed?</span></span> <span data-ttu-id="44a6b-127">ダウンロードの手順とコマンドレットの構文については、「[Windows PowerShell による Azure AD の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44a6b-127">See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="44a6b-128">モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="44a6b-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

  <span data-ttu-id="44a6b-129">この例では、 **Enterprise E3 ライセンス** と、 **電話システム** および **国内通話プラン** ライセンスを割り当てています。</span><span class="sxs-lookup"><span data-stu-id="44a6b-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

  <span data-ttu-id="44a6b-130">スクリプト内のライセンスの名前または製品名は、斜体で表示されています (下記の例と、その次の「 **スクリプトで使用される電話システムと通話プランの製品名または SKU** 」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="44a6b-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="44a6b-131">スクリプトで使用される電話システムと通話プランの製品名または SKU</span><span class="sxs-lookup"><span data-stu-id="44a6b-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="44a6b-132">**製品名**</span><span class="sxs-lookup"><span data-stu-id="44a6b-132">**Product name**</span></span>|<span data-ttu-id="44a6b-133">**SKU 部品名**</span><span class="sxs-lookup"><span data-stu-id="44a6b-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="44a6b-134">エンタープライズ E5 (電話システムあり)</span><span class="sxs-lookup"><span data-stu-id="44a6b-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="44a6b-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="44a6b-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="44a6b-136">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="44a6b-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="44a6b-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="44a6b-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="44a6b-138">エンタープライズ E1</span><span class="sxs-lookup"><span data-stu-id="44a6b-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="44a6b-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="44a6b-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="44a6b-140">Skype for Business オンライン スタンドアロンプラン 2</span><span class="sxs-lookup"><span data-stu-id="44a6b-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="44a6b-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="44a6b-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="44a6b-142">電話システム</span><span class="sxs-lookup"><span data-stu-id="44a6b-142">Phone System</span></span>  <br/> |<span data-ttu-id="44a6b-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="44a6b-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="44a6b-144">国際通話プラン</span><span class="sxs-lookup"><span data-stu-id="44a6b-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="44a6b-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="44a6b-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="44a6b-146">国内通話プラン</span><span class="sxs-lookup"><span data-stu-id="44a6b-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="44a6b-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="44a6b-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="44a6b-148">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="44a6b-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="44a6b-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="44a6b-149">MCOPSTNPP</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="44a6b-150">電話会議: ライセンス割り当てのヒントとスクリプト</span><span class="sxs-lookup"><span data-stu-id="44a6b-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="44a6b-151">電話会議のライセンス割り当て前に知っておくべき情報</span><span class="sxs-lookup"><span data-stu-id="44a6b-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="44a6b-p109">**サードパーティの電話会議プロバイダー**: サードパーティの電話会議プロバイダーを使用するように他のユーザーによって既に設定されている場合に、 **電話会議**ライセンスを割り当てると、電話会議プロバイダーとして Microsoft を使用するように変更されます。この設定を変更して、サードパーティ プロバイダーに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="44a6b-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="44a6b-154">次のステップ: **電話会議**ライセンスを割り当てたら、電話会議プロバイダーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="44a6b-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign a audio conferencing provider.</span></span> <span data-ttu-id="44a6b-155">[Microsoft を電話会議プロバイダーとして割り当てる]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44a6b-155">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="44a6b-156">電話会議ライセンスを 1 人のユーザーに対して割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="44a6b-156">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="44a6b-p111">手順は Office 365 ライセンスを割り当てる場合と同じです。「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44a6b-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="44a6b-159">電話会議ライセンスを一括で割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="44a6b-159">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="44a6b-160">[IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="44a6b-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="44a6b-p112">**Windows Azure Active Directory モジュール** をダウンロードしてインストールします。ダウンロードの手順とコマンドレットの構文については、「[Windows PowerShell による Azure AD の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44a6b-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="44a6b-163">モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="44a6b-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="44a6b-164">スクリプト内のライセンスまたは製品名は、斜体で表示されています。</span><span class="sxs-lookup"><span data-stu-id="44a6b-164">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="44a6b-165">すべての製品名については、「[スクリプトで使用される電話会議の製品名または SKU](assign-skype-for-business-and-microsoft-teams-licenses.md#sku)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44a6b-165">See [Dial-in conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="44a6b-166">この例では、Enterprise E3 ライセンスと電話会議ライセンスを割り当てています。</span><span class="sxs-lookup"><span data-stu-id="44a6b-166">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="44a6b-167">スクリプトで使用される電話会議の製品名または SKU</span><span class="sxs-lookup"><span data-stu-id="44a6b-167">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="44a6b-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="44a6b-168"><a name="sku"> </a></span></span>

|<span data-ttu-id="44a6b-169">**製品名**</span><span class="sxs-lookup"><span data-stu-id="44a6b-169">**Product name**</span></span>|<span data-ttu-id="44a6b-170">**SKU 部品名**</span><span class="sxs-lookup"><span data-stu-id="44a6b-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="44a6b-171">電話会議</span><span class="sxs-lookup"><span data-stu-id="44a6b-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="44a6b-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="44a6b-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="44a6b-173">Skype for Business オンライン スタンドアロンプラン 2</span><span class="sxs-lookup"><span data-stu-id="44a6b-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="44a6b-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="44a6b-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="44a6b-175">エンタープライズ E1</span><span class="sxs-lookup"><span data-stu-id="44a6b-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="44a6b-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="44a6b-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="44a6b-177">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="44a6b-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="44a6b-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="44a6b-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="44a6b-179">Enterprise E5 (電話会議なし)</span><span class="sxs-lookup"><span data-stu-id="44a6b-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="44a6b-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="44a6b-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="44a6b-181">Enterprise E5 (電話会議あり)</span><span class="sxs-lookup"><span data-stu-id="44a6b-181">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="44a6b-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="44a6b-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="44a6b-183">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="44a6b-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="44a6b-184">コミュニケーション クレジットのライセンス割り当て前に知っておくべき情報</span><span class="sxs-lookup"><span data-stu-id="44a6b-184">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="44a6b-185">**Enterprise E5 のお客様**: ユーザーに Enterprise E5 ライセンスが割り当てられている場合でも、ユーザーに **コミュニケーション クレジット**のライセンスを割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="44a6b-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communication Credits** licenses.</span></span>
    
- <span data-ttu-id="44a6b-186">**次のステップ**: これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="44a6b-186">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="44a6b-187">詳しい手順については、「[通話プランのセットアップ](/microsoftteams/set-up-calling-plans)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44a6b-187">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="44a6b-188">通信クレジットのライセンスを 1 人のユーザーに対して割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="44a6b-188">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="44a6b-p115">手順は Office 365 ライセンスを割り当てる場合と同じです。「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44a6b-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="44a6b-191">コミュニケーション クレジットのライセンスを一括で割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="44a6b-191">How to assign Communication Credits licenses in bulk</span></span>

<span data-ttu-id="44a6b-p116">**電話会議**ライセンスを割り当てるサンプル スクリプトを確認します。その情報を、 **コミュニケーション クレジット**のライセンスを割り当てるための情報で更新します。</span><span class="sxs-lookup"><span data-stu-id="44a6b-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="44a6b-194">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="44a6b-194">Related topics</span></span>
  
[<span data-ttu-id="44a6b-195">通話プランのセットアップ</span><span class="sxs-lookup"><span data-stu-id="44a6b-195">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="44a6b-196">利用可能残高を追加してコミュニケーション クレジットを管理する</span><span class="sxs-lookup"><span data-stu-id="44a6b-196">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
