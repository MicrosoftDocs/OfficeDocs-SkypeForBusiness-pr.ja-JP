---
title: Teams のライセンスを割り当てる
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: オーディオ会議、電話システムのような機能や、通話プランは、ライセンスを割り当てる方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46966b7cad855ef6336b501564cde89dffd6b2b2
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993630"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="e132a-103">マイクロソフトのチームのライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e132a-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="e132a-104">オーディオ会議、電話システム、および計画を呼び出すような機能をユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e132a-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="e132a-105">この資料では、一括では個々 のユーザーに対してこれらのライセンスを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e132a-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e132a-106">参照してください[マイクロソフト チームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)についてはどのようなライセンスを購入する必要があり、Office 365 によって、それらを購入する方法を計画、オーディオ会議、フリー ダイヤル番号、および社内外の電話番号を呼び出すこと、ユーザーが取得するためです。</span><span class="sxs-lookup"><span data-stu-id="e132a-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="e132a-107">電話システムと通話プラン: ライセンス割り当てのヒントとスクリプト</span><span class="sxs-lookup"><span data-stu-id="e132a-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="e132a-108">ここでは、オーディオ会議、電話システム、および計画を呼び出してライセンスを割り当てる前に知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e132a-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="e132a-109">**使用してオンプレミス ハイブリッド ユーザーに PSTN 接続しますか。**</span><span class="sxs-lookup"><span data-stu-id="e132a-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="e132a-110">その場合は、のみ、電話システムのライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e132a-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="e132a-111">割り当てる必要がありますいない呼び出して計画します。</span><span class="sxs-lookup"><span data-stu-id="e132a-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="e132a-112">**ライセンスの割り当て後の待機時間**: Office 365 とマイクロソフトのチームとの間の遅延時間のために割り当てる計画を呼び出してライセンスを割り当てると、ユーザーには、最大で 24 時間をかかることができます。</span><span class="sxs-lookup"><span data-stu-id="e132a-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="e132a-113">24 時間後に計画を呼び出すことがユーザーに割り当てされていない、[ビジネス製品の管理のヘルプのサポートに連絡](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してください。</span><span class="sxs-lookup"><span data-stu-id="e132a-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="e132a-p104">**エラー メッセージ**: 正確な数のライセンスを購入していないとエラー メッセージが表示されます。追加の通話プランのライセンスを購入する必要がある場合は、[ **追加購入**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e132a-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="e132a-116">**次の手順**: ユーザーに通話プランのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e132a-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="e132a-117">詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e132a-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="e132a-118">1 人のユーザーを呼び出すことを計画し、電話システムのライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e132a-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="e132a-119">手順は Office 365 ライセンスを割り当てる場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="e132a-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="e132a-120">「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e132a-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="e132a-121">一括を呼び出すことを計画し、電話システムのライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e132a-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="e132a-122">Microsoft オンライン サービス サインイン アシスタント RTW の IT プロフェッショナルのためにインストールします。</span><span class="sxs-lookup"><span data-stu-id="e132a-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="e132a-123">このモジュールがインストールされていない場合は、</span><span class="sxs-lookup"><span data-stu-id="e132a-123">Don't have the module installed?</span></span> <span data-ttu-id="e132a-124">[IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) を参照してダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="e132a-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="e132a-125">Windows Azure Active Directory のモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e132a-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="e132a-126">このモジュールがインストールされていない場合は、</span><span class="sxs-lookup"><span data-stu-id="e132a-126">Don't have the module installed?</span></span> <span data-ttu-id="e132a-127">ダウンロードの手順とコマンドレットの構文については、 [Windows PowerShell を使用して AD を Azure の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e132a-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="e132a-128">モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e132a-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="e132a-129">この例では、 Enterprise E3 ライセンス と、 電話システム および 国内通話プラン ライセンスを割り当てています。</span><span class="sxs-lookup"><span data-stu-id="e132a-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="e132a-130">斜体が (を参照してください、[電話システムおよび製品名の計画を呼び出すまたは Sku のスクリプト作成に使用](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)することも、例の後) では、ライセンスの名前、またはスクリプト内で製品名が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e132a-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="e132a-131">スクリプトで使用される電話システムと通話プランの製品名または SKU</span><span class="sxs-lookup"><span data-stu-id="e132a-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="e132a-132">製品名</span><span class="sxs-lookup"><span data-stu-id="e132a-132">Product name</span></span> | <span data-ttu-id="e132a-133">SKU 部品名</span><span class="sxs-lookup"><span data-stu-id="e132a-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="e132a-134">エンタープライズ E5 (電話システムあり)</span><span class="sxs-lookup"><span data-stu-id="e132a-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="e132a-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="e132a-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="e132a-136">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="e132a-136">Enterprise E3</span></span> | <span data-ttu-id="e132a-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="e132a-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="e132a-138">エンタープライズ E1</span><span class="sxs-lookup"><span data-stu-id="e132a-138">Enterprise E1</span></span> | <span data-ttu-id="e132a-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="e132a-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="e132a-140">電話システム</span><span class="sxs-lookup"><span data-stu-id="e132a-140">Phone System</span></span> | <span data-ttu-id="e132a-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="e132a-141">MCOEV</span></span> |
| <span data-ttu-id="e132a-142">国内 & の国際通話プラン</span><span class="sxs-lookup"><span data-stu-id="e132a-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="e132a-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="e132a-143">MCOPSTN2</span></span> |
| <span data-ttu-id="e132a-144">国内の呼び出し (u. s./PR/CA で、eu 加盟国のユーザーまたは 1 か月あたりの 1200 分のユーザーまたは 1 か月あたり 3000 分) の計画</span><span class="sxs-lookup"><span data-stu-id="e132a-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="e132a-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="e132a-145">MCOPSTN1</span></span> |
| <span data-ttu-id="e132a-146">国内の呼び出し (120 分単位/月単位のユーザーのそれぞれの国) の計画</span><span class="sxs-lookup"><span data-stu-id="e132a-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="e132a-147">*注: この計画では米国で*。</span><span class="sxs-lookup"><span data-stu-id="e132a-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="e132a-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="e132a-148">MCOPSTN5</span></span> |
| <span data-ttu-id="e132a-149">国内の呼び出し (240 分単位/月単位のユーザーのそれぞれの国) の計画</span><span class="sxs-lookup"><span data-stu-id="e132a-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="e132a-150">*注: この計画では米国で*。</span><span class="sxs-lookup"><span data-stu-id="e132a-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="e132a-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="e132a-151">MCOPSTN6</span></span> |
| <span data-ttu-id="e132a-152">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="e132a-152">Communications Credits</span></span> | <span data-ttu-id="e132a-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="e132a-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="e132a-154">オーディオ会議: ヒントとライセンスの割り当てのためのスクリプト</span><span class="sxs-lookup"><span data-stu-id="e132a-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="e132a-155">ここでは、オーディオ会議のライセンスを割り当てる前に知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e132a-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="e132a-156">**サードパーティの電話会議プロバイダー**: サードパーティの電話会議プロバイダーを使用するように他のユーザーによって既に設定されている場合に、 電話会議ライセンスを割り当てると、電話会議プロバイダーとして Microsoft を使用するように変更されます。</span><span class="sxs-lookup"><span data-stu-id="e132a-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="e132a-157">この設定を変更して、サードパーティ プロバイダーに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="e132a-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="e132a-158">**次の手順**: オーディオ会議のライセンスを割り当てると、する必要があります、オーディオ会議プロバイダーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e132a-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="e132a-159">[オーディオ会議プロバイダーとしてのマイクロソフトの割り当て](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e132a-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="e132a-160">オーディオ会議のライセンスを 1 つのユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e132a-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="e132a-161">手順は Office 365 ライセンスを割り当てる場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="e132a-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="e132a-162">「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e132a-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="e132a-163">一括で電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e132a-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="e132a-164">[IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="e132a-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="e132a-165">Windows Azure Active Directory モジュール をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="e132a-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="e132a-166">ダウンロードの手順とコマンドレットの構文については、 [Windows PowerShell を使用して AD を Azure の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e132a-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="e132a-167">モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e132a-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="e132a-168">イタリック体では、ライセンスの名前、またはスクリプト内で製品名が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e132a-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="e132a-169">[オーディオ会議の製品名やスクリプト作成に使用する製品](#audio-conferencing-product-names-or-skus-used-for-scripting)のすべての製品名を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e132a-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="e132a-170">この例では、Enterprise E3 ライセンスと電話会議ライセンスを割り当てています。</span><span class="sxs-lookup"><span data-stu-id="e132a-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="e132a-171">オーディオ会議の製品名または SKU のスクリプト作成に使用</span><span class="sxs-lookup"><span data-stu-id="e132a-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="e132a-172">製品名</span><span class="sxs-lookup"><span data-stu-id="e132a-172">Product name</span></span> | <span data-ttu-id="e132a-173">SKU 部品名</span><span class="sxs-lookup"><span data-stu-id="e132a-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="e132a-174">オーディオ会議 (サブスクリプション)</span><span class="sxs-lookup"><span data-stu-id="e132a-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="e132a-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="e132a-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="e132a-176">オーディオ会議を支払うあたり 1 分 (従量)</span><span class="sxs-lookup"><span data-stu-id="e132a-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="e132a-177">*注: 通信のクレジットを設定し、有効にする必要があります*。</span><span class="sxs-lookup"><span data-stu-id="e132a-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="e132a-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="e132a-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="e132a-179">エンタープライズ E1</span><span class="sxs-lookup"><span data-stu-id="e132a-179">Enterprise E1</span></span> | <span data-ttu-id="e132a-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="e132a-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="e132a-181">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="e132a-181">Enterprise E3</span></span> | <span data-ttu-id="e132a-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="e132a-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="e132a-183">Enterprise E5 (電話会議なし)</span><span class="sxs-lookup"><span data-stu-id="e132a-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="e132a-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="e132a-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="e132a-185">Enterprise E5 (電話会議あり)</span><span class="sxs-lookup"><span data-stu-id="e132a-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="e132a-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="e132a-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="e132a-187">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="e132a-187">Communications Credits</span></span>

<span data-ttu-id="e132a-188">ここでは、通信のクレジットのライセンスを割り当てる前に知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e132a-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="e132a-189">**E5 のエンタープライズのお客様**: ユーザーがエンタープライズ E5 のライセンスを割り当てられている場合でもをお勧めするユーザーを割り当てる通信のクレジットのライセンスです。</span><span class="sxs-lookup"><span data-stu-id="e132a-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="e132a-190">**次のステップ**: これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e132a-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="e132a-191">詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e132a-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="e132a-192">通信のクレジットのライセンスを 1 つのユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e132a-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="e132a-193">手順は Office 365 ライセンスを割り当てる場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="e132a-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="e132a-194">「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e132a-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="e132a-195">大量の通信のクレジットのライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e132a-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="e132a-196">電話会議ライセンスを割り当てるサンプル スクリプトを確認します。</span><span class="sxs-lookup"><span data-stu-id="e132a-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="e132a-197">その情報を、 通信クレジットのライセンスを割り当てるための情報で更新します。</span><span class="sxs-lookup"><span data-stu-id="e132a-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e132a-198">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e132a-198">Related topics</span></span>

[<span data-ttu-id="e132a-199">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="e132a-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="e132a-200">資金を追加してコミュニケーション クレジットを管理する</span><span class="sxs-lookup"><span data-stu-id="e132a-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
