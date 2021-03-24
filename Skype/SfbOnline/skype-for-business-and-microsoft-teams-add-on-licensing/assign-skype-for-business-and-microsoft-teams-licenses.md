---
title: ユーザーに会議 ID を割り当てる
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: '電話システム、電話会議、通話プランやコミュニケーション クレジットを使用するために Skype for Business  のライセンスを割り当てる方法について説明します。 '
ms.openlocfilehash: beb4fa46133aa7a09ce3d0de0a08392dbf2d2591
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106493"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="1fb93-103">ユーザーに会議 ID を割り当てる</span><span class="sxs-lookup"><span data-stu-id="1fb93-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="1fb93-104">この記事では、電話会議、電話システム、通話プランのような機能のライセンスをユーザーに割り当てる方法についてヒントを提供します。</span><span class="sxs-lookup"><span data-stu-id="1fb93-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="1fb93-105">また、ライセンスを一括で割り当てるスクリプトも提供します。</span><span class="sxs-lookup"><span data-stu-id="1fb93-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fb93-106">Microsoft 365 または Office 365 プランに応じて、購入する必要があるライセンスと購入方法の詳細については[、Skype for Business](skype-for-business-and-microsoft-teams-add-on-licensing.md)アドオン ライセンスを参照してください。そのため、ユーザーは電話会議、無料電話番号、社外の電話番号に電話する機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="1fb93-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Microsoft 365 or Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="1fb93-107">電話システムと通話プラン: ライセンス割り当てのヒントとスクリプト</span><span class="sxs-lookup"><span data-stu-id="1fb93-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="1fb93-108">電話会議、電話システム、通話プランのライセンスを割り当てる前に知る必要がある情報</span><span class="sxs-lookup"><span data-stu-id="1fb93-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="1fb93-p102">**ハイブリッド ユーザー向けにオンプレミス PSTN 接続を使用している場合** 、 **電話システム** のライセンスのみをユーザーに割り当てる必要があります。通話プランを割り当てる必要は **ありません** 。</span><span class="sxs-lookup"><span data-stu-id="1fb93-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="1fb93-112">ライセンスの割り当て後の **待機時間:** Microsoft 365 または Office 365 と Skype for Business Online の間に遅延時間が発生するために、ライセンスを割り当てた後にユーザーに通話プランが割り当てられるまで、最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1fb93-112">**Latency after assigning licenses**: Because of the latency between Microsoft 365 or Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="1fb93-113">24 時間がたってユーザーに通話プランが割り当てられていない場合は、ビジネス製品のサポートにお問い合 [わせください - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="1fb93-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="1fb93-p104">**エラー メッセージ**: 正確な数のライセンスを購入していないとエラー メッセージが表示されます。追加の通話プランのライセンスを購入する必要がある場合は、[ **追加購入**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1fb93-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="1fb93-116">**次の手順**: ユーザーに通話プランのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fb93-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="1fb93-117">詳しい手順については、「[通話プランのセットアップ](/microsoftteams/set-up-calling-plans)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1fb93-117">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="1fb93-118">電話システムおよび通話プランのライセンスを 1 人のユーザーに対して割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="1fb93-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="1fb93-119">手順は、Microsoft 365 または 365 ライセンスを割り当てるOffice同じです。</span><span class="sxs-lookup"><span data-stu-id="1fb93-119">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="1fb93-120">「 [一ビジネス向け Microsoft 365 のライセンスを割り当てる、または削除する」を参照してください](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="1fb93-120">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="1fb93-121">電話システムおよび通話プランのライセンスを一括で割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="1fb93-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="1fb93-122">IT プロフェッショナル **向け Microsoft Online Services Sign-In RTW をインストールします**。</span><span class="sxs-lookup"><span data-stu-id="1fb93-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="1fb93-123">このモジュールがインストールされていない場合は、</span><span class="sxs-lookup"><span data-stu-id="1fb93-123">Don't have the module installed?</span></span> <span data-ttu-id="1fb93-124">[IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) を参照してダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="1fb93-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="1fb93-125">Windows **Azure Active Directory モジュールをインストールします。**</span><span class="sxs-lookup"><span data-stu-id="1fb93-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="1fb93-126">このモジュールがインストールされていない場合は、</span><span class="sxs-lookup"><span data-stu-id="1fb93-126">Don't have the module installed?</span></span> <span data-ttu-id="1fb93-127">ダウンロード [手順とコマンドレットの構文については、「ADを使用](/previous-versions/azure/jj151815(v=azure.100)) Windows PowerShell Azure Windows PowerShellを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb93-127">See [Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="1fb93-128">モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1fb93-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="1fb93-129">この例では、 **Enterprise E3 ライセンス** と、 **電話システム** および **国内通話プラン** ライセンスを割り当てています。</span><span class="sxs-lookup"><span data-stu-id="1fb93-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="1fb93-130">スクリプト内のライセンスの名前または製品名は、斜体で表示されています (下記の例と、その次の「 **スクリプトで使用される電話システムと通話プランの製品名または SKU** 」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="1fb93-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="1fb93-131">スクリプトで使用される電話システムと通話プランの製品名または SKU</span><span class="sxs-lookup"><span data-stu-id="1fb93-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="1fb93-132">**製品名**</span><span class="sxs-lookup"><span data-stu-id="1fb93-132">**Product name**</span></span>|<span data-ttu-id="1fb93-133">**SKU 部品名**</span><span class="sxs-lookup"><span data-stu-id="1fb93-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fb93-134">エンタープライズ E5 (電話システムあり)</span><span class="sxs-lookup"><span data-stu-id="1fb93-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="1fb93-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="1fb93-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="1fb93-136">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="1fb93-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="1fb93-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="1fb93-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="1fb93-138">エンタープライズ E1</span><span class="sxs-lookup"><span data-stu-id="1fb93-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="1fb93-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="1fb93-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="1fb93-140">Skype for Business オンライン スタンドアロンプラン 2</span><span class="sxs-lookup"><span data-stu-id="1fb93-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="1fb93-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="1fb93-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="1fb93-142">電話システム</span><span class="sxs-lookup"><span data-stu-id="1fb93-142">Phone System</span></span>  <br/> |<span data-ttu-id="1fb93-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="1fb93-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="1fb93-144">国際通話プラン</span><span class="sxs-lookup"><span data-stu-id="1fb93-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="1fb93-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="1fb93-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="1fb93-146">国内通話プラン (米国 3000 分/ EU 1200 分プラン)</span><span class="sxs-lookup"><span data-stu-id="1fb93-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="1fb93-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="1fb93-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="1fb93-148">国内通話プラン (120 分の通話プラン)</span><span class="sxs-lookup"><span data-stu-id="1fb93-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="1fb93-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="1fb93-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="1fb93-150">国内通話プラン (240 分通話プラン)</span><span class="sxs-lookup"><span data-stu-id="1fb93-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="1fb93-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="1fb93-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="1fb93-152">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="1fb93-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="1fb93-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="1fb93-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="1fb93-154">電話会議: ライセンス割り当てのヒントとスクリプト</span><span class="sxs-lookup"><span data-stu-id="1fb93-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="1fb93-155">電話会議のライセンス割り当て前に知っておくべき情報</span><span class="sxs-lookup"><span data-stu-id="1fb93-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="1fb93-p109">**サードパーティの電話会議プロバイダー**: サードパーティの電話会議プロバイダーを使用するように他のユーザーによって既に設定されている場合に、 **電話会議** ライセンスを割り当てると、電話会議プロバイダーとして Microsoft を使用するように変更されます。この設定を変更して、サードパーティ プロバイダーに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="1fb93-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="1fb93-158">次の手順: 電話会議ライセンス **を割** り当て後、電話会議プロバイダーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fb93-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="1fb93-159">[Microsoft を電話会議プロバイダーとして割り当てる]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb93-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="1fb93-160">電話会議ライセンスを 1 人のユーザーに対して割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="1fb93-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="1fb93-161">手順は、Microsoft 365 または 365 ライセンスを割り当てるOffice同じです。</span><span class="sxs-lookup"><span data-stu-id="1fb93-161">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="1fb93-162">「 [一ビジネス向け Microsoft 365 のライセンスを割り当てる、または削除する」を参照してください](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="1fb93-162">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="1fb93-163">電話会議ライセンスを一括で割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="1fb93-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="1fb93-164">[IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="1fb93-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="1fb93-p112">**Windows Azure Active Directory モジュール** をダウンロードしてインストールします。ダウンロードの手順とコマンドレットの構文については、「[Windows PowerShell による Azure AD の管理](/previous-versions/azure/jj151815(v=azure.100))」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1fb93-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="1fb93-167">モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1fb93-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="1fb93-168">スクリプト内のライセンスまたは製品名は、斜体で表示されています。</span><span class="sxs-lookup"><span data-stu-id="1fb93-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="1fb93-169">すべての [製品名のスクリプトで使用される電話会議](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) の製品名または SKU を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb93-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="1fb93-170">この例では、Enterprise E3 ライセンスと電話会議ライセンスを割り当てています。</span><span class="sxs-lookup"><span data-stu-id="1fb93-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="1fb93-171">スクリプトで使用される音声会議の製品名または SKU</span><span class="sxs-lookup"><span data-stu-id="1fb93-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="1fb93-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="1fb93-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="1fb93-173">**製品名**</span><span class="sxs-lookup"><span data-stu-id="1fb93-173">**Product name**</span></span>|<span data-ttu-id="1fb93-174">**SKU 部品名**</span><span class="sxs-lookup"><span data-stu-id="1fb93-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fb93-175">電話会議</span><span class="sxs-lookup"><span data-stu-id="1fb93-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="1fb93-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="1fb93-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="1fb93-177">Skype for Business オンライン スタンドアロンプラン 2</span><span class="sxs-lookup"><span data-stu-id="1fb93-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="1fb93-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="1fb93-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="1fb93-179">エンタープライズ E1</span><span class="sxs-lookup"><span data-stu-id="1fb93-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="1fb93-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="1fb93-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="1fb93-181">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="1fb93-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="1fb93-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="1fb93-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="1fb93-183">Enterprise E5 (電話会議なし)</span><span class="sxs-lookup"><span data-stu-id="1fb93-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="1fb93-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="1fb93-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="1fb93-185">Enterprise E5 (電話会議あり)</span><span class="sxs-lookup"><span data-stu-id="1fb93-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="1fb93-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="1fb93-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="1fb93-187">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="1fb93-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="1fb93-188">通信クレジットのライセンス割り当て前に知っておくべき情報</span><span class="sxs-lookup"><span data-stu-id="1fb93-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="1fb93-189">**Enterprise E5 のお客様**: ユーザーに Enterprise E5 ライセンスが割り当てられている場合でも、通信クレジット ライセンスを割り当 **てすることをお勧** めします。</span><span class="sxs-lookup"><span data-stu-id="1fb93-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="1fb93-190">**次のステップ**: これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fb93-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="1fb93-191">詳しい手順については、「[通話プランのセットアップ](/microsoftteams/set-up-calling-plans)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1fb93-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="1fb93-192">通信クレジットのライセンスを 1 人のユーザーに対して割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="1fb93-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="1fb93-193">手順は、Microsoft 365 または 365 ライセンスを割り当てるOffice同じです。</span><span class="sxs-lookup"><span data-stu-id="1fb93-193">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="1fb93-194">「 [一ビジネス向け Microsoft 365 のライセンスを割り当てる、または削除する」を参照してください](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="1fb93-194">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="1fb93-195">通信クレジット ライセンスを一括で割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="1fb93-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="1fb93-196">**電話会議** ライセンスを割り当てるサンプル スクリプトを確認します。</span><span class="sxs-lookup"><span data-stu-id="1fb93-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="1fb93-197">その情報を、 **通信クレジット** のライセンスを割り当てるための情報で更新します。</span><span class="sxs-lookup"><span data-stu-id="1fb93-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1fb93-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fb93-198">Related topics</span></span>
  
[<span data-ttu-id="1fb93-199">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="1fb93-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="1fb93-200">資金を追加してコミュニケーション クレジットを管理する</span><span class="sxs-lookup"><span data-stu-id="1fb93-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
