---
title: Teams アドオン ライセンスをユーザーに割り当てる
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Teams アドオン ライセンスをユーザーに割り当て、電話会議、電話システム、通話プランのような機能をユーザーに割り当てる方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240672b125190492a036bc9dfa3f7a42070e8320
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116935"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="e0575-103">Teams アドオン ライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e0575-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="e0575-104">アドオン ライセンスは、電話会議、電話システム、通話プランなどの特定の Teams 機能のライセンスです。</span><span class="sxs-lookup"><span data-stu-id="e0575-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="e0575-105">この記事では、アドオン ライセンスを個々のユーザーと多数のユーザーに一括で割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0575-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="e0575-106">アドオン [ライセンスで利用できる](./microsoft-teams-add-on-licensing.md) Teams 機能の Teams アドオン ライセンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0575-106">See [Teams add-on licensing](./microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="e0575-107">また、購入する必要があるライセンスと購入方法 (プランに応じて異なります) に関する情報も表示され、ユーザーは電話会議、無料電話番号、組織外の電話番号に電話する機能などの機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="e0575-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="e0575-108">ユーザーに必要な機能を決めたら、ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0575-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="e0575-109">Microsoft 365 管理センターまたは PowerShell を使用して、組織内のユーザーにライセンスを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="e0575-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="e0575-110">ライセンスを管理するには、グローバル管理者またはユーザー管理管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0575-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="e0575-111">電話システム、通話プラン、および通信クレジットのライセンスを割り当てる前に知る必要がある情報</span><span class="sxs-lookup"><span data-stu-id="e0575-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="e0575-112">始める前に、次の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e0575-112">Before you get started, review the following requirements:</span></span>

- <span data-ttu-id="e0575-113">ハイブリッド ユーザーにオンプレミスの公衆交換電話網 (PSTN) 接続を使用している場合は、電話システム ライセンスのみを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0575-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="e0575-114">通話プランライセンスを割り当てない。</span><span class="sxs-lookup"><span data-stu-id="e0575-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="e0575-115">Microsoft 365 と Microsoft Teams の間に遅延時間が生じ、ライセンスの割り当て後にユーザーに通話プランが割り当てられるまで、最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0575-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="e0575-116">ユーザーに通話プランが 24 時間割り当てられていない場合は、ビジネス製品のサポートに問い合 [わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。</span><span class="sxs-lookup"><span data-stu-id="e0575-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="e0575-117">正しい数のライセンスを購入していない場合は、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0575-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="e0575-118">追加の通話プラン ライセンスを購入する必要がある場合は、追加購入するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0575-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="e0575-119">ユーザーに Enterprise E5 ライセンスが割り当てられている場合でも[](../what-are-communications-credits.md)、PSTN から通話を発信または受信する場合は、通信クレジット ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0575-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want to make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="e0575-120">通話プランまたはコミュニケーション クレジットのライセンスをユーザーに割り当てると、組織の電話番号を取得し、その番号をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0575-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="e0575-121">詳しい手順については、「[通話プランのセットアップ](../set-up-calling-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e0575-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="e0575-122">Microsoft 365 管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="e0575-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="e0575-123">Microsoft 365 管理センターを使用して、一度に個別のユーザーまたは小規模なユーザー セットにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e0575-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="e0575-124">ライセンスの割り当ては、[ **ライセンス]** ページ (一度に最大 20 人のユーザー) または [アクティブなユーザー] **ページで行** います。</span><span class="sxs-lookup"><span data-stu-id="e0575-124">You assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="e0575-125">選択する方法は、特定のユーザーの製品ライセンスを管理するか、特定の製品のユーザー ライセンスを管理するかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e0575-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="e0575-126">詳しい手順については、「ライセンスをユーザーに割り当てる [」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="e0575-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="e0575-127">数百から数千のユーザーなど、多数のユーザーにライセンスを割り当てる必要がある場合は [、Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign)で PowerShell またはグループベースのライセンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0575-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="e0575-128">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="e0575-128">Using PowerShell</span></span>

<span data-ttu-id="e0575-129">PowerShell を使用して、ライセンスをユーザーに一括で割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e0575-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="e0575-130">詳細については、「PowerShell でライセンスを [ユーザー アカウントに割り当てる」を参照してください](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e0575-130">To learn more, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="e0575-131">スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="e0575-131">Example script</span></span>

<span data-ttu-id="e0575-132">スクリプトを使用してユーザーにライセンスを割り当てる方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e0575-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="e0575-133">IT プロフェッショナル向けサインイン アシスタント RTW Microsoft Online Services [64 ビット版をインストールします](/collaborate/connect-redirect?DownloadID=59185)。</span><span class="sxs-lookup"><span data-stu-id="e0575-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](/collaborate/connect-redirect?DownloadID=59185).</span></span>
2. <span data-ttu-id="e0575-134">次の手順に合った Microsoft Azure Active Directory モジュールをWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e0575-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="e0575-135">管理者特権のコマンド プロンプトWindows PowerShell開きます (管理者としてWindows PowerShell実行します)。</span><span class="sxs-lookup"><span data-stu-id="e0575-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="e0575-136">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0575-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="e0575-137">NuGet プロバイダーをインストールするように求めるメッセージが表示されたら **、「Y」** と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e0575-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="e0575-138">PSGallery からモジュールをインストールするように求めるメッセージが表示されたら **、「Y」** と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e0575-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="e0575-139">コマンド プロンプトWindows PowerShell、次のスクリプトを実行してユーザーにライセンスを割り当て、組織名と割り当てるライセンスの識別子を \<CompanyName:License> 割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0575-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="e0575-140">たとえば、litwareinc:MCOMEETADV などです。</span><span class="sxs-lookup"><span data-stu-id="e0575-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="e0575-141">識別子は、ライセンスの表示名とは異なります。</span><span class="sxs-lookup"><span data-stu-id="e0575-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="e0575-142">たとえば、電話会議の識別子は MCOMEETADV です。</span><span class="sxs-lookup"><span data-stu-id="e0575-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="e0575-143">詳細については、ライセンスの [製品名と SKU 識別子を参照してください](#product-names-and-sku-identifiers-for-licensing)。</span><span class="sxs-lookup"><span data-stu-id="e0575-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    <span data-ttu-id="e0575-144">たとえば、Microsoft 365 Enterprise 1 および電話会議ライセンスを割り当てるには、スクリプトで次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0575-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="e0575-145">Microsoft Business Voice (通話プランなし) ライセンスを割り当てるには、スクリプトで次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0575-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="e0575-146">ライセンスの製品名と SKU 識別子</span><span class="sxs-lookup"><span data-stu-id="e0575-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="e0575-147">ここでは、PowerShell を使用して Teams でライセンスを管理するときに参照として使用できる製品名とそれに対応する SKU パーツ名の一覧の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="e0575-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="e0575-148">詳細については[、「PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)でライセンスとサービスを表示する[](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)」、ライセンスの製品名とサービス プラン識別子[、Education SKU](../sku-reference-edu.md)リファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0575-148">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="e0575-149">製品名</span><span class="sxs-lookup"><span data-stu-id="e0575-149">Product name</span></span>| <span data-ttu-id="e0575-150">SKU 部品名</span><span class="sxs-lookup"><span data-stu-id="e0575-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="e0575-151">Microsoft Enterprise E5 (電話システムを使用)</span><span class="sxs-lookup"><span data-stu-id="e0575-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="e0575-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="e0575-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="e0575-153">Microsoft Enterprise E5 (電話会議なし)</span><span class="sxs-lookup"><span data-stu-id="e0575-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="e0575-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="e0575-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="e0575-155">Microsoft Enterprise E5 (電話会議付き)</span><span class="sxs-lookup"><span data-stu-id="e0575-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="e0575-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="e0575-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="e0575-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="e0575-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="e0575-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="e0575-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="e0575-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="e0575-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="e0575-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="e0575-160">STANDARDPACK</span></span> |
| <span data-ttu-id="e0575-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="e0575-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="e0575-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="e0575-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="e0575-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="e0575-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="e0575-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="e0575-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="e0575-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="e0575-165">Microsoft 365 Business</span></span> | <span data-ttu-id="e0575-166">SPB</span><span class="sxs-lookup"><span data-stu-id="e0575-166">SPB</span></span>|
| <span data-ttu-id="e0575-167">Microsoft Business Voice (カナダ)</span><span class="sxs-lookup"><span data-stu-id="e0575-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="e0575-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="e0575-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="e0575-169">Microsoft Business Voice (英国)</span><span class="sxs-lookup"><span data-stu-id="e0575-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="e0575-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="e0575-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="e0575-171">Microsoft Business Voice (米国)</span><span class="sxs-lookup"><span data-stu-id="e0575-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="e0575-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="e0575-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="e0575-173">Microsoft Business Voice (通話プランなし)</span><span class="sxs-lookup"><span data-stu-id="e0575-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="e0575-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="e0575-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="e0575-175">米国向け Microsoft Business Voice (通話プランなし)</span><span class="sxs-lookup"><span data-stu-id="e0575-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="e0575-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="e0575-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="e0575-177">電話会議</span><span class="sxs-lookup"><span data-stu-id="e0575-177">Audio Conferencing</span></span> | <span data-ttu-id="e0575-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="e0575-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="e0575-179">電話会議の分単位支払い (移動に合った支払い)</span><span class="sxs-lookup"><span data-stu-id="e0575-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="e0575-180">*通信クレジットを設定して有効にする必要があります。*</span><span class="sxs-lookup"><span data-stu-id="e0575-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="e0575-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="e0575-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="e0575-182">電話システム</span><span class="sxs-lookup"><span data-stu-id="e0575-182">Phone System</span></span> | <span data-ttu-id="e0575-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="e0575-183">MCOEV</span></span> |
| <span data-ttu-id="e0575-184">国内通話と国際通話プラン</span><span class="sxs-lookup"><span data-stu-id="e0575-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="e0575-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="e0575-185">MCOPSTN2</span></span> |
| <span data-ttu-id="e0575-186">国内通話プラン (米国/PR/CA の場合はユーザー/月あたり 3000 分、EU 各国の場合はユーザー/月あたり 1200 分)</span><span class="sxs-lookup"><span data-stu-id="e0575-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="e0575-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="e0575-187">MCOPSTN1</span></span> |
| <span data-ttu-id="e0575-188">国内通話プラン (各国のユーザー/月あたり 120 分)</span><span class="sxs-lookup"><span data-stu-id="e0575-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="e0575-189">*このプランは、米国ではご利用になられません。*</span><span class="sxs-lookup"><span data-stu-id="e0575-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="e0575-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="e0575-190">MCOPSTN5</span></span> |
| <span data-ttu-id="e0575-191">国内通話プラン (国ごとにユーザー/月あたり 240 分)</span><span class="sxs-lookup"><span data-stu-id="e0575-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="e0575-192">*このプランは、米国ではご利用になられません。*</span><span class="sxs-lookup"><span data-stu-id="e0575-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="e0575-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="e0575-193">MCOPSTN6</span></span> |
| <span data-ttu-id="e0575-194">コミュニケーション クレジット</span><span class="sxs-lookup"><span data-stu-id="e0575-194">Communications Credits</span></span> | <span data-ttu-id="e0575-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="e0575-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e0575-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0575-196">Related topics</span></span>

- [<span data-ttu-id="e0575-197">Teams アドオンのライセンス</span><span class="sxs-lookup"><span data-stu-id="e0575-197">Teams add-on licensing</span></span>](./microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="e0575-198">Teams へのユーザー アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="e0575-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="e0575-199">PowerShell でライセンスとサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="e0575-199">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="e0575-200">ライセンスのための製品名とサービス プラン識別子</span><span class="sxs-lookup"><span data-stu-id="e0575-200">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="e0575-201">Education SKU リファレンス</span><span class="sxs-lookup"><span data-stu-id="e0575-201">Education SKU reference</span></span>](../sku-reference-edu.md)