---
title: Teams のライセンスを割り当てる
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 電話会議、電話システム、通話プランなどの機能にライセンスを割り当てる方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 55d85aae6540c6b5888be848ad08d686bd0da2b1
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905069"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="f9cdf-103">Microsoft Teams ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f9cdf-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="f9cdf-104">電話会議、電話システム、通話プランなどの機能については、ユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="f9cdf-105">この記事では、これらのライセンスを一括で追加する方法と個々のユーザー用に追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f9cdf-106">購入する必要があるライセンスと購入方法の詳細については、「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。 Office 365 プランによっては、電話会議、無料電話番号、ビジネス以外の電話番号への通話が可能です。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="f9cdf-107">電話システムと通話プラン: ライセンス割り当てのヒントとスクリプト</span><span class="sxs-lookup"><span data-stu-id="f9cdf-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="f9cdf-108">電話会議、電話システム、通話プランのライセンスを割り当てる前に知っておくべきことを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-108">Here's what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="f9cdf-109">**ハイブリッドユーザー用にオンプレミスの PSTN 接続を使用している場合**</span><span class="sxs-lookup"><span data-stu-id="f9cdf-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="f9cdf-110">その場合は、電話システムのライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="f9cdf-111">通話プランを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="f9cdf-112">**ライセンスの割り当て後の待機時間**: Office 365 と Microsoft Teams の間の待機時間のため、ライセンスを割り当てた後にユーザーが通話プランを割り当てられるまでに最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="f9cdf-113">24時間後にユーザーに通話プランが割り当てられていない場合は、「一般[法人向け製品サポートへのお問い合わせ-管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="f9cdf-p104">**エラー メッセージ**: 正確な数のライセンスを購入していないとエラー メッセージが表示されます。追加の通話プランのライセンスを購入する必要がある場合は、[ **追加購入**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="f9cdf-116">**次の手順**: ユーザーに通話プランのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="f9cdf-117">詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="f9cdf-118">電話システムと通話プランのライセンスを1人のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="f9cdf-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="f9cdf-119">手順は Office 365 ライセンスを割り当てる場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="f9cdf-120">「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="f9cdf-121">電話システムと通話プランのライセンスを一括で割り当てる</span><span class="sxs-lookup"><span data-stu-id="f9cdf-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="f9cdf-122">IT プロフェッショナル向け Microsoft Online Service サインインアシスタントプロフェッショナル用 RTWHTTP://GO.MICROSOFT.COM/FWLINK/?LINKID=625123 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="f9cdf-123">このモジュールがインストールされていない場合は、</span><span class="sxs-lookup"><span data-stu-id="f9cdf-123">Don't have the module installed?</span></span> <span data-ttu-id="f9cdf-124">[IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) を参照してダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="f9cdf-125">Windows Azure Active Directory モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="f9cdf-126">このモジュールがインストールされていない場合は、</span><span class="sxs-lookup"><span data-stu-id="f9cdf-126">Don't have the module installed?</span></span> <span data-ttu-id="f9cdf-127">ダウンロード手順とコマンドレットの構文については、「 [Windows PowerShell を使用した AZURE AD の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="f9cdf-128">モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="f9cdf-129">この例では、 Enterprise E3 ライセンス と、 電話システム および 国内通話プラン ライセンスを割り当てています。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="f9cdf-130">スクリプトに含まれているライセンス名または製品名が斜体で表示されます (「[電話システムと通話プランの製品名、または](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)、例の後にスクリプトで使用される sku を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

```powershell
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

## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="f9cdf-131">スクリプトで使用される電話システムと通話プランの製品名または SKU</span><span class="sxs-lookup"><span data-stu-id="f9cdf-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="f9cdf-132">製品名</span><span class="sxs-lookup"><span data-stu-id="f9cdf-132">Product name</span></span> | <span data-ttu-id="f9cdf-133">SKU 部品名</span><span class="sxs-lookup"><span data-stu-id="f9cdf-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="f9cdf-134">エンタープライズ E5 (電話システムあり)</span><span class="sxs-lookup"><span data-stu-id="f9cdf-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="f9cdf-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="f9cdf-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="f9cdf-136">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="f9cdf-136">Enterprise E3</span></span> | <span data-ttu-id="f9cdf-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="f9cdf-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="f9cdf-138">エンタープライズ E1</span><span class="sxs-lookup"><span data-stu-id="f9cdf-138">Enterprise E1</span></span> | <span data-ttu-id="f9cdf-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="f9cdf-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="f9cdf-140">電話システム</span><span class="sxs-lookup"><span data-stu-id="f9cdf-140">Phone System</span></span> | <span data-ttu-id="f9cdf-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="f9cdf-141">MCOEV</span></span> |
| <span data-ttu-id="f9cdf-142">国内 & 国際通話プラン</span><span class="sxs-lookup"><span data-stu-id="f9cdf-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="f9cdf-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="f9cdf-143">MCOPSTN2</span></span> |
| <span data-ttu-id="f9cdf-144">国内通話プラン (米国/PR/月額プランの場合はユーザーあたり、1ヶ月あたり3000分、EU 諸国の場合はユーザー/月あたり1200分)</span><span class="sxs-lookup"><span data-stu-id="f9cdf-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="f9cdf-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="f9cdf-145">MCOPSTN1</span></span> |
| <span data-ttu-id="f9cdf-146">国内通話プラン (各国のユーザー/月あたり120分)</span><span class="sxs-lookup"><span data-stu-id="f9cdf-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="f9cdf-147">*注: このプランはご利用いただけません*。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="f9cdf-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="f9cdf-148">MCOPSTN5</span></span> |
| <span data-ttu-id="f9cdf-149">国内通話プラン (各国のユーザー/月あたり240分)</span><span class="sxs-lookup"><span data-stu-id="f9cdf-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="f9cdf-150">*注: このプランはご利用いただけません*。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="f9cdf-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="f9cdf-151">MCOPSTN6</span></span> |
| <span data-ttu-id="f9cdf-152">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="f9cdf-152">Communications Credits</span></span> | <span data-ttu-id="f9cdf-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="f9cdf-153">MCOPSTNPP</span></span> | 

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="f9cdf-154">電話会議ライセンスを1人のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="f9cdf-154">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="f9cdf-155">手順は Office 365 ライセンスを割り当てる場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-155">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="f9cdf-156">「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-156">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="f9cdf-157">電話会議ライセンスを一括で割り当てる</span><span class="sxs-lookup"><span data-stu-id="f9cdf-157">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="f9cdf-158">[IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://go.microsoft.com/fwlink/?LinkId=625123) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-158">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="f9cdf-159">Windows Azure Active Directory モジュール をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-159">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="f9cdf-160">ダウンロード手順とコマンドレットの構文については、「 [Windows PowerShell を使用した AZURE AD の管理](https://go.microsoft.com/fwlink/p/?LinkId=320628)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-160">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="f9cdf-161">モジュールをインストールしたら、Windows PowerShell のコマンド プロンプトと次の構文を使って、ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-161">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="f9cdf-162">スクリプト内のライセンス名または製品名が斜体で表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-162">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="f9cdf-163">すべての製品名の[スクリプトに使用されている電話会議の製品名または sku](#audio-conferencing-product-names-or-skus-used-for-scripting)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-163">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="f9cdf-164">この例では、Enterprise E3 ライセンスと電話会議ライセンスを割り当てています。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-164">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

```powershell
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

## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="f9cdf-165">スクリプトで使用される電話会議の製品名または SKU</span><span class="sxs-lookup"><span data-stu-id="f9cdf-165">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="f9cdf-166">製品名</span><span class="sxs-lookup"><span data-stu-id="f9cdf-166">Product name</span></span> | <span data-ttu-id="f9cdf-167">SKU 部品名</span><span class="sxs-lookup"><span data-stu-id="f9cdf-167">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="f9cdf-168">電話会議 (サブスクリプション)</span><span class="sxs-lookup"><span data-stu-id="f9cdf-168">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="f9cdf-169">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="f9cdf-169">MCOMEETADV</span></span> | 
| <span data-ttu-id="f9cdf-170">電話会議の1分あたりの料金 (プリペイド)</span><span class="sxs-lookup"><span data-stu-id="f9cdf-170">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="f9cdf-171">*注: 通信クレジットを設定して有効にする必要があり*ます。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-171">*Note: Requires Communications Credits to be set up and enabled*.</span></span> |    <span data-ttu-id="f9cdf-172">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="f9cdf-172">MCOMEETACPEA</span></span> |
| <span data-ttu-id="f9cdf-173">エンタープライズ E1</span><span class="sxs-lookup"><span data-stu-id="f9cdf-173">Enterprise E1</span></span> | <span data-ttu-id="f9cdf-174">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="f9cdf-174">STANDARDPACK</span></span> | 
| <span data-ttu-id="f9cdf-175">エンタープライズ E3</span><span class="sxs-lookup"><span data-stu-id="f9cdf-175">Enterprise E3</span></span> | <span data-ttu-id="f9cdf-176">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="f9cdf-176">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="f9cdf-177">Enterprise E5 (電話会議なし)</span><span class="sxs-lookup"><span data-stu-id="f9cdf-177">Enterprise E5 (without Audio Conferencing)</span></span> |     <span data-ttu-id="f9cdf-178">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="f9cdf-178">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="f9cdf-179">Enterprise E5 (電話会議あり)</span><span class="sxs-lookup"><span data-stu-id="f9cdf-179">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="f9cdf-180">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="f9cdf-180">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="f9cdf-181">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="f9cdf-181">Communications Credits</span></span>

<span data-ttu-id="f9cdf-182">通信クレジットのライセンスを割り当てる前に知っておくべきことを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-182">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="f9cdf-183">**Enterprise e5 のお客様**: ユーザーに enterprise e5 ライセンスが割り当てられている場合でも、通信クレジットのライセンスを割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-183">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="f9cdf-184">**次のステップ**: これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号を組織内のユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-184">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="f9cdf-185">詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-185">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="f9cdf-186">1人のユーザーに通信クレジットのライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f9cdf-186">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="f9cdf-187">手順は Office 365 ライセンスを割り当てる場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-187">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="f9cdf-188">「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-188">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="f9cdf-189">通信クレジットのライセンスを一括で割り当てる</span><span class="sxs-lookup"><span data-stu-id="f9cdf-189">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="f9cdf-190">電話会議ライセンスを割り当てるサンプル スクリプトを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-190">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="f9cdf-191">その情報を、 通信クレジットのライセンスを割り当てるための情報で更新します。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-191">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f9cdf-192">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9cdf-192">Related topics</span></span>

[<span data-ttu-id="f9cdf-193">通話プランの設定</span><span class="sxs-lookup"><span data-stu-id="f9cdf-193">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="f9cdf-194">資金を追加してコミュニケーション クレジットを管理する</span><span class="sxs-lookup"><span data-stu-id="f9cdf-194">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
